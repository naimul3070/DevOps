
#### Check hardware clock
    sudo hwclock


#### If your system time is different than your hardware clock time, you can use the --systohc option to change the hardware clock to the current system clock time.
    sudo hwclock --systohc
    
#### It also works the other way around. To set the system clock time from the hardware clock use the --hctosys option.
    sudo hwclock --hctosys
    
#### List available time zones with the following command. Pick one relevant to your location, and we’ll configure your system to that time zone in the next step.
    timedatectl list-timezones
    
#### Use the grep command to narrow down the search. In the example below this command will produce a list of all available time zones in Australia.
    timedatectl list-timezones | grep Dhaka
    
#### Once you’ve picked the correct time zone from the list, use the following syntax to set your system’s time zone.
    sudo timedatectl set-timezone Asia/Dhaka
    
#### To turn time synchronization on or off, use the respective command below.
    sudo timedatectl set-ntp on
#### OR
    sudo timedatectl set-ntp off
    
#### If these commands don’t work, you need to uninstall the NTP package and install systemd-timesyncd. The following command will do both things.
    sudo apt remove ntp
    
#### If you’d like to set the system clock to some arbitrary date and time, ensure that time synchronization is off (as we’ve shown above) and use the following date command. This command will set the date and time to 10 January 2021, 12:00 PM, but substitute any values you want.
    sudo date -s "4 APR 2022 10:00:00"

#### Happy Linux
