# Adding Kernel Parameters to GRUB

Press ``e`` when the menu shows up and add them on the ``linux`` line:

    linux /boot/vmlinuz-linux root=UUID=978e3e81-8048-4ae1-8a06-aa727458e8ff quiet splash

Press ``b`` to boot with these parameters.

To make the change persistent after reboot, while you could manually edit
``/boot/grub/grub.cfg`` with the exact line from above, the best practice is to:

Edit ``/etc/default/grub`` and append your kernel options to the
``GRUB_CMDLINE_LINUX_DEFAULT`` line:

    GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"

And then automatically re-generate the ``grub.cfg`` file with:

    # grub-mkconfig -o /boot/grub/grub.cfg
