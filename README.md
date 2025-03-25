# Creating a custom ringtone in Cisco Jabber
*This is written referencing the Windows 11 version of Cisco Jabber (version 14.1.2.57135)*

The Cisco Jabber app requires that any audio file present in its Cisco Systems\Cisco Jabber\Sounds\Ringtones directory to be a .WAV file with a bitrate of 384 kbps with one one channel (mono). If the file does not meet these requirements, the app will not display your file in the app's dropdown.

Below is a detailing of how to achieve this end.

1. Find an audio file of your choosing. The initial format shouldn't matter.
2. Import the audio file into an audio editor of your choice. [Audacity](https://www.audacityteam.org/) will be used as reference but the end goal is the same.
3. When you are happy with the audio file's length, volume, or other properties, export it with the following in mind:
    1. The file MUST be in mono.
    2. The file MUST have a bitrate of 384 kbps.
        - This can be achieved by understanding the following forumla for calculating the bitrate of audio:
            $bitrate = sample\ rate * bit\ depth * \ number\ of\ channels$
            - Sample rate is typically in **Hz**.
            - Bit depth is called "Encoding" in Audacity, and it is usually measured in a certain number of **bits**.
        - For example, I can achieve a 384 kbps bitrate audio file if I export the file with the following: $24000\ Hz * 16\ bits * 1\ channel = 384000\ bps \ or\  384\ kbps$.
    3. The file MUST be of the .WAV format.
### At this point, the steps for adding the ringtone will differ if you are on Windows or MacOS
#### Windows
4. When you have the exported audio file, it must be placed in the following directory: C:\Program Files (x86)\Cisco Systems\Cisco Jabber\Sounds\Ringtones. Go to Cisco Jabber, click the gear icon (located in the top right corner), click "Settings", select the "Notifications" category, scroll down to ringtone, and select your custom ringtone from the drop down. I believe all custom ringtones will be located at the bottom of the list, but check thoroughly just in case it isn't there.
    - The ringtone will have the same name as the file name.

#### MacOS
4. Navigate to Cisco Jabber\Contents\Resources\Sounds. Create a new folder named "Ringtones". Cisco is really strange for this next bit: pick an already existing ringtone (located in the above /Sounds directory), copy its name, delete it, and rename your new ringtone with that name. Now, put your newly renamed custom ringtone into the /Ringtones folder. Relaunch your Jabber and look for it in the sound settings.
    - Click "Preferences" > "Notifications" > Go to the **Ringtone** section and look for the name of the already existing sound that you replaced.