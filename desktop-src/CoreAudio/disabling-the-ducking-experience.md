---
Description: 'A user can disable the Default Ducking Experience provided by the system by using the options that are available on the Communications tab of the Windows multimedia control panel, Mmsys.cpl.'
ms.assetid: '5604b927-99f8-450f-a48c-b38d782584de'
title: Disabling the Default Ducking Experience
---

# Disabling the Default Ducking Experience

A user can disable the [Default Ducking Experience](stream-attenuation.md) provided by the system by using the options that are available on the **Communications** tab of the Windows multimedia control panel, Mmsys.cpl.

When ducking is applied, a fade-out and fade-in effect is used for a period of 1 second. A game application might not want the communication stream to interfere with the game audio. Some media applications might find that the playback experience is jarring when music fades back in. These types of applications can choose not to participate in the ducking experience.

Programmatically, a direct WASAPI client can opt out by using the session manager for the audio session that provides volume control for the non-communication streams. Note that even if an client opts out of ducking, it still receives ducking notifications from the system.

To opt out of ducking, the client must get a reference to the [**IAudioSessionControl2**](iaudiosessioncontrol2.md) interface of the session manager. To opt out of the ducking experience, use the following steps:

1.  Instantiate the device enumerator and use it to get a reference to the endpoint of the device that the media application is using to render the non-communication stream.
2.  Activate the session manager from the device endpoint and get a reference to the [**IAudioSessionManager2**](iaudiosessionmanager2.md) interface of the session manager.
3.  By using the [**IAudioSessionManager2**](iaudiosessionmanager2.md) pointer, get a reference to the [**IAudioSessionControl**](iaudiosessioncontrol.md) interface of the session manager.
4.  Query for the [**IAudioSessionControl2**](iaudiosessioncontrol2.md) from the [**IAudioSessionControl**](iaudiosessioncontrol.md) interface.
5.  Call [**IAudioSessionControl2::SetDuckingPreference**](iaudiosessioncontrol2-setduckingpreference.md) and pass **TRUE** or **FALSE** to specify the the ducking preference. The specified preference can be changed dynamically during the session. Note that the opt-out change does not take effect until the stream is stopped and started again.

The following code shows how an application can specify its ducking preference. The caller of the function must pass **TRUE** or **FALSE** in the DuckingOptOutChecked parameter. Depending on the value passed, ducking is enabled or disabled through the [**IAudioSessionControl2::SetDuckingPreference**](iaudiosessioncontrol2-setduckingpreference.md).


```C++
////////////////////////////////////////////////////////////////////
//Description: Specifies the ducking options for the application.
//Parameters: 
//    If DuckingOptOutChecked is TRUE system ducking is disabled; 
//    FALSE, system ducking is enabled.
////////////////////////////////////////////////////////////////////

HRESULT DuckingOptOut(bool DuckingOptOutChecked)
{
    HRESULT hr = S_OK;

    IMMDeviceEnumerator* pDeviceEnumerator NULL;
    IMMDevice* pEndpoint = NULL;
    IAudioSessionManager2* pSessionManager2 = NULL;
    IAudioSessionControl* pSessionControl = NULL;
    IAudioSessionControl2* pSessionControl2 = NULL;


    //  Start with the default endpoint.

    hr = CoCreateInstance(__uuidof(MMDeviceEnumerator), 
                          NULL, 
                          CLSCTX_INPROC_SERVER, 
                          IID_PPV_ARGS(&amp;pDeviceEnumerator));
    
    if (SUCCEEDED(hr))
    {
        hr = pDeviceEnumerator>GetDefaultAudioEndpoint(eRender, eConsole, &amp;pEndpoint);

        pDeviceEnumerator>Release();
        pDeviceEnumerator = NULL;
    }

    // Activate session manager.
    if (SUCCEEDED(hr))
    {
        hr = pEndpoint->Activate(__uuidof(IAudioSessionManager2), 
                                 CLSCTX_INPROC_SERVER,
                                 NULL, 
                                 reinterpret_cast<void **>(&amp;pSessionManager2));
        pEndpoint->Release();
        pEndpoint = NULL;
    }
    if (SUCCEEDED(hr))
    {
        hr = pSessionManager2->GetAudioSessionControl(NULL, 0, &amp;pSessionControl);
        
        pSessionManager2->Release();
        pSessionManager2 = NULL;
    }

    if (SUCCEEDED(hr))
    {
        hr = pSessionControl->QueryInterface(
                  __uuidof(IAudioSessionControl2),
                  (void**)&amp;pSessionControl2);
                
        pSessionControl->Release();
        pSessionControl = NULL;
    }

    //  Sync the ducking state with the specified preference.

    if (SUCCEEDED(hr))
    {
        if (DuckingOptOutChecked)
        {
            hr = pSessionControl2->SetDuckingPreference(TRUE);
        }
        else
        {
            hr = pSessionControl2->SetDuckingPreference(FALSE);
        }
        pSessionControl2->Release();
        pSessionControl2 = NULL;
    }
    return hr;
}
```



## Related topics

<dl> <dt>

[Using a Communication Device](using-the-communication-device.md)
</dt> <dt>

[Default Ducking Experience](stream-attenuation.md)
</dt> <dt>

[Providing a Custom Ducking Behavior](providing-a-custom-ducking-experience.md)
</dt> <dt>

[Implementation Considerations for Ducking Notifications](handling-audio-ducking-events-from-communication-devices.md)
</dt> <dt>

[Getting Ducking Events](getting-ducking-events-from-a-communication-device.md)
</dt> </dl>

 

 


