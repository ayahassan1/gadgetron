
=========
Gadgetron
=========

Credit::

    Fabrice Poupon <fabrice.poupon@cea.fr>
    Antoine Grigis <antoine.grigis@cea.fr>


The `Gadgetron <http://gadgetron.github.io/>`_ is an open source framework for medical image reconstruction. It has been developed at the National Heart, Lung, and Blood Institute, NIH, Bethesda, MD, USA and at the Department of Computer Science and Department of Clinical Medicine, Aarhus University, Denmark.


CEA install
===========

Here is a procedure to install the gadgetron on your CEA Windows 7 professional computer.

Install requirements
--------------------

1. Install ``Virtual clone drive`` (both utilities) from::

   ftp://ftp.cea.fr/pub/unati/gadgetron/VirtualCloneDrive-5.5/SetupVirtualCloneDrive5500.exe

2. ``Configure your file browser``: Option des dossiers et de recherche -> Affichage -> décocher utiliser assistant partage.

3. Install ``Visual Studio 2008 Express`` in 'C:\\MSVS2008' (problem with SQL server install -> uncheck) from::

   ftp://ftp.cea.fr/pub/unati/gadgetron/VS2008-Express-withSP1/vcsetup.exe

4. Install ``KB2538243`` patch from::

   ftp://ftp.cea.fr/pub/unati/gadgetron/Windows-redistributables/KB2538243/vcredist_x64.exe

5. Install ``redistributable 8.0.50727.42 VC++-2005 x86`` from::

   ftp://ftp.cea.fr/pub/unati/gadgetron/Windows-redistributables/redistVC2005-8.0.50727.42/vcredist_x86.exe

6. Install ``Microsoft Windows SDK 6.1`` in 'C:\\WinSDK\\Windows\\v6.1' (install custom, select developer Tools, default) from::

   ftp://ftp.cea.fr/pub/unati/gadgetron/WindowsSDK-v6.1/Setup.exe

7. Install ``Windows driver kit 7.1`` using Virtual Clone Drive from::

   ftp://ftp.cea.fr/pub/unati/gadgetron/WindowsWDDK-7.1/GRMWDK_EN_7600_1.ISO

8. ``File manipulation``:

   - Create folders 'atlmfc\\include' and 'atlmfc\\lib\\amd64' in 'C:\\MSVS2008\\VC'.

   - Copy 'Wddk\\inc\\atl71' and 'Wddk\\inc\\mfc42' folders content in 'MSVS2008\\VC\atlmfc\\include':
   
         * atlconv.h (keep atl)
         * atldef.h (keep atl)

   - Copy 'Wddk\lib\atl\i386' and 'Wddk\lib\mfc\i386' folders content in 'MSVS2008\\VC\\atlmfc\\lib'.

   - Copy 'Wddk\lib\atl\amd64' and 'Wddk\lib\mfc\amd64' folders content in 'MSVS2008\\VC\\atlmfc\\lib\\amd64'.

9. ``Activate the virtualization`` in the BIOS settings if not already activated: VT-x/AMD-V; SVM (Secure Virtual Machine).


Install optionals
-----------------

10. ``Install NSIS`` from::

    ftp://ftp.cea.fr/pub/unati/gadgetron/NSIS/nsis-2.50-setup.exe

11. ``Install NSIS editor`` from::

    ftp://ftp.cea.fr/pub/unati/gadgetron/NSIS/nisedit2.0.3.exe


Install & configure IDEA
------------------------

12. ``Install IDEA`` using Virtual Clone Drive from::

    ftp://ftp.cea.fr/pub/unati/gadgetron/Siemens-IDEA-VE11/IDEA_VE11B.iso

    Create a shortcut from 'C:\\MIDEA\bin\\IDEA.cmd' to the desktop (IDEA.Net) and update icon.

13. ``Change the mount type`` from 'cifs' to 'vboxsf':

    - Edit file 'C:\\MIDEA\\N4_VE11B_LATEST_20150530\\n4\\pkg\\MrApplications\\MrIDEA\\VMAddons\\mntview.sh':
    
         * 144: MountType=vboxsf
         * 225: options="" 
         * 224: mountSource=$shareName

    - Add a 'SnapshotView' shared folder to VB mars machine pointing to 'C:\MIDEA\N4_VE11B_LATEST_20150530'. Edit 'C:\\MIDEA\\VM_VE11B\\.VirtualBox\\Machines\\mars\\mars.xml':
    
         * 53::

            <SharedFolders>
                <SharedFolder name="SnapshotView" hostPath="C:\MIDEA\N4_VE11B_LATEST_20150530" writable="true"/>
            </SharedFolders>

14. ``First execution of the 'IDEA.Net' application``, select scanner::

        sys
        select PRISMA-XR (3)



