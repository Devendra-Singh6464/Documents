``` d
WB_CP_231   ------>  all done store room.
cpu135-A20  -------->  all done / ip: 192.168.15.183 / store room.
wb_cp_237 ------>  all done / ip:  / store room.
CPU183-D21 ------>  all done / ip: 192.168.15.205 (seat no. 071).
WB_CP_9   -------->   all done no.003 (Ibell cpu). 
CPU182-D21 -------> all done seat no.1005 / ip: 192.168.15.115
free IP's list --------> 192.168.15.152,175,198,212
192.168.15.246 ------> all done / CPU258-B23 / store room(12cr).
192.168.15.156 ------> all done / CPU180-D21 / store room(12cr).
192.168.15.202 -----> all done / WB_CPU_3 / seat no.104 (only ssd installd).
192.168.15.90 ------> all done / WB_CP_132 / seat no.013
192.168.15.238 ------> all done / CPU83-A19 / seat no.36
``` 

``` d
5 floor

seat no: 375 / WB_CPU_240(WB_CP_240) : ip:192.168.5.86 / all done
seat no: 328 /  WB_CP_187 : ip:192.168.5.111 / all done
seat no: 340 / WB_CPU_64 [wb_cp_64]/ all done
seat no: 376 / cpu146-A20 / all done
seat no: 363 / WB_CP_173 / all done
seat no: 366 / cpu135-A20 / all done
seat no: 388 / cpu170-k20 / all done


store room 5 floor / wb_cpu_10 / 
store room 5 floor / wb_cpu_29 / all done

```







```bash
192.168.10.0 to 192.168.10.255 range network free IP.
192.168.10.245 
192.168.15.185 seat no.64 : WB_CP_213
```


```bash
---- windows Desktop -- IP: 192.168.15.168 seat(04)
 
---- Akeneo Mac mini 
IP:- 192.168.15.128
seat no:- 1004
User: webkul
Password: webkul123
```


## Ready laptops:
----------------------------

laptop ready: LP109-H21, lp35 


joining : MCP25-L21,
MKB25-L21
1. MMO25-L21

free IP : 192.168.15.182 used / wb_cp_237
192.168.15.183 used / cpu135-A20
192.168.15.185  used /cp_231
192.168.15.186 :  use mac mini store room we used 
192.168.15.187


192.168.10.210: macp11 old ip 

MCP12 --- try  mac 
 

### Step 3: Restart PulseAudio

1. **Stop PulseAudio**:
    
    bash
    
    Copy code
    
    `pulseaudio -k`
    
2. **Start PulseAudio** again:
    
    bash
    
    Copy code
    
    `pulseaudio --start`
    
3. Check if your sound devices appear in the **Settings > Sound** menu after restarting PulseAudio.
    

### Step 4: Reinstall ALSA and PulseAudio

If restarting doesn’t work, try reinstalling the audio packages.

1. **Reinstall ALSA and PulseAudio**:
    
    bash
    
    Copy code
    
    `sudo apt update sudo apt install --reinstall alsa-base pulseaudio`
    
2. **Restart your computer** to apply changes.
    

### Step 5: Verify Audio Modules Are Loaded

Make sure the necessary kernel modules are loaded for your audio hardware:

1. Run the following command to load the `snd_hda_intel` module (commonly used for Intel sound devices):
    
    bash
    
    Copy code
    
    `sudo modprobe snd_hda_intel`
    
2. Check your sound settings again to see if the audio devices are detected.
    

### Step 6: Check for Additional Drivers

1. Open **Software & Updates** and go to the **Additional Drivers** tab.
2. Check if there’s an audio driver available for your device, and install it if available.

### Step 7: Update the Kernel (if Necessary)

If the issue persists and you're using an older kernel, try updating to a newer version, as newer kernels often have improved hardware support.

1. To install the latest stable kernel, run:
    
    bash
    
    Copy code
    
    `sudo apt update sudo apt upgrade`