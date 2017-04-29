# ansible-retropie
Ansible 2.x compatible role for configuration / maintaining a Retropie installation on a Raspberry Pi 3

Raspberry Pi Initial Configuration

  - Write the RetroPie image to an SD card and boot the Raspberry Pi
  - Press F4 to exit EmulationStation
  - `passwd`
    - `raspberry`
    - Enter new password
    - Enter new password again
  - If configuring a DHCP reservation for IP persistence
    - Determine MAC address for the network adapter of choice
    - `sudo ifconfig`
      - Look for `HWaddr` under `wlan0` if using wifi
      - Look for `HWaddr` under `eth0` if using ethernet
    - Configure DHCP reservation on router / switch per the manufacturers instructions
  - Configure wifi (if necessary)
    - `sudo RetroPie-Setup/retropie_setup.sh`
      - `C`
      - `835 - wifi - Configure Wifi`
      - `1`
      - Select wireless SSID
      - Enter wireless password
      - `<Exit>`
      - `<Back>`
      - `<Exit>`
  - If configuring a static IP address for IP persistence
    - Follow the tutorial here:  https://www.modmypi.com/blog/how-to-give-your-raspberry-pi-a-static-ip-address-update
  - Verify that the assigned / configured IP address is correct
    - sudo ifconfig
      - Look for `inet addr` under `wlan0` if using wifi
      - Look for `inet addr` under `eth0` if using ethernet
  - Enable SSH access
    - `sudo raspi-config`
    - `Interfacing Options`
    - `SSH`
    - `<Yes>`
    - `<Finish>`
    - `sudo reboot`

Ansible Configuration
