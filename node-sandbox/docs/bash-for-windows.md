# Install Bash for Windows 10 Anniversary Update

## Update your computer to Windows 10 Anniversary Update

The following steps walk you through installing the Windows 10 Anniversary Update on your computer using Windows Update:

1. From the Windows Run box, start the Windows Settings app.

1. Select **Update & security**.

	![Update & Security settings](./media/bash-for-windows/windows-settings.png)

1. Select **Check for updates**.

1. Once the update descriptions have been downloaded, the Windows 10 update will be listed as build 1607 (or later). Select **Install now**.

	![](./media/bash-for-windows/windows-update.png)

	Once you select **Install now**, a progress bar displays the current status of the update process.
 
## Install Bash for Windows 

The following steps walk you through installing the Bash environment from Windows 10 Anniversary Update:

1. From the Windows Run box, start the Windows Settings app.

1. Select **Update & security**.

	![Update & Security settings](./media/bash-for-windows/windows-settings.png)

1. In the left menu, select **For developers**.

1. Under **Use developer features**, select **Developer mode**.

	![Developer mode](./media/bash-for-windows/developer-mode.png)

1. On the **Use developer features** confirmation dialog, select **Yes**

	![developer-mode-confirm.png](./media/bash-for-windows/developer-mode-confirm.png)

1. Close the **Settings** application.

1. Open the **Control Panel**.

1. Select **Programs**.

	![Control Panel](./media/bash-for-windows/control-panel.png)

1. Select **Turn Windows features on or off**.

	![Control Panel Programs applet](./media/bash-for-windows/control-panel-programs.png)
 
1. Select **Windows Subsystem for Linux (Beta)**.

	![Windows features dialog](./media/bash-for-windows/windows-features.png)

1. If prompted to reboot your computer, select **Restart now**.

1. After your computer reboots, and you log into Windows, open the Windows Run box, and type `bash.exe`. Select the **bash.exe** result.

	![Run bash](./media/bash-for-windows/run-bash.png)

1. In the command window (that displays when you select bash.exe), type `y` and press **Enter** to download and install Bash from the Windows Store.

	![Bash downloading](./media/bash-for-windows/bash-downloading.png) 

1. When you are prompted to create a default UNIX user account, enter a username in the required field, and press **Enter**. The account does not have to match your Windows account, and it can't be `admin`.

	![bash Unix name](./media/bash-for-windows/bash-unix-name.png)

1. Enter (and confirm) a password for the username you entered.

1. Close the command prompt. Now, if you type `bash` into the Windows Run box, you'll see that it has been installed. As with any Windows desktop application, you can right-click it, and, from the context menu, pin the application icon to the Start menu or taskbar.   

	![Bash installed](./media/bash-for-windows/bash-installed.png)

## Next steps

- [Download and install Azure NuGet packages](packages.md)