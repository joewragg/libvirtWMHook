# libvirtWMHook
Window manager for libvirt, qemu and kvm. Moves windows and sets resolution automatically when starting the virtual machine. Using xrandr and python.

When the VM is started the qemu script calls the start script.
When the VM is shutdown the qemu script calls the end script.

start, end and qemu scripts should be placed in or symlinked to /etc/libvirt/hooks.

monitorsStart and monitorsEnd can be called by the start and end scripts respectively.

Each monitors script sets the monitors required resolution and turns on and off displays if needed using xrandr.

The start script also starts synergy client for mouse input, stops the corsair daemon so the keyboard can be passed throught to the VM; kills steam and sets the background to the right monitor's image.

The end script kills synergy client, restarts the corsair keyboard daemon and sets the background to a multimonitor combinartion of two backgrounds.
