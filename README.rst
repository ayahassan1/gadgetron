
=========
Gadgetron
=========

Credit: Fabrice Poupon <fabrice.poupon@cea.fr>
        Antoine Grigis <antoine.grigis@cea.fr>


The `Gadgetron <http://gadgetron.github.io/>`_ is an open source framework for medical image reconstruction. It has been developed at the National Heart, Lung, and Blood Institute, NIH, Bethesda, MD, USA and at the Department of Computer Science and Department of Clinical Medicine, Aarhus University, Denmark.


CEA install
===========

Here is a procedure to install the gadgetron on your CEA Windows 7 professional computer.

Install requirements
--------------------

.. note::

    Virtual clone drive: install both utilities from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/VirtualCloneDrive-5.5/SetupVirtualCloneDrive5500.exe>`_.

.. note::

    Configure your file browser: Option des dossiers et de recherche -> Affichage -> décocher utiliser assistant partage.

.. note::

    Visual Studio 2008 Express: install tool in 'C:\MSVS2008' from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/VS2008-Express-withSP1/vcsetup.exe>`_ (problem with SQL server install -> uncheck).

.. note::

    KB2538243: install patch from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/Windows-redistributables/KB2538243/vcredist_x64.exe>`_.

.. note::

    Redistributable 8.0.50727.42 VC++-2005 x86: install redistributable from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/Windows-redistributables/redistVC2005-8.0.50727.42/vcredist_x86.exe>`_.

.. note::

    Microsoft Windows SDK 6.1: install tool in 'C:\WinSDK\Windows\v6.1' from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/WindowsSDK-v6.1/Setup.exe>`_ (install custom, select developer Tools: default).

.. note::

    Windows driver kit 7.1: install from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/WindowsWDDK-7.1/GRMWDK_EN_7600_1.ISO>`_ using Virtual Clone Drive.

.. note::
    
    Create folders 'atlmfc\include' and 'atlmfc\lib\amd64' in 'C:\MSVS2008\VC'.
    Copy 'Wddk\inc\atl71' and 'Wddk\inc\mfc42' folders content in 'MSVS2008\VC\atlmfc\include':  
        * atlconv.h (keep atl)
        * atldef.h (keep atl)
    Copy 'Wddk\lib\atl\i386' and 'Wddk\lib\mfc\i386' folders content in 'MSVS2008\VC\atlmfc\lib'.
    Copy 'Wddk\lib\atl\amd64' and 'Wddk\lib\mfc\amd64' folders content in 'MSVS2008\VC\atlmfc\lib\amd64'.

.. warning::

    Activate the virtualization in the BIOS settings if not already activated: VT-x/AMD-V; SVM (Secure Virtual Machine).


Install optionals
-----------------

.. note::

    Install NSIS from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/NSIS/nsis-2.50-setup.exe>`_.

.. note::

    Install (HM NIS EDIT) NSIS editor from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/NSIS/nisedit2.0.3.exe>`_.


Install & configure IDEA
------------------------

.. note::

    Install IDEA from `here <ftp://ftp.cea.fr/pub/unati/gadgetron/Siemens-IDEA-VE11/IDEA_VE11B.iso>`_ using Virtual Clone Drive.
    Create a shortcut from 'C:\MIDEA\bin\IDEA.cmd' to the desktop (IDEA.Net) and update icon.

.. note::
    
    Change the mont type from 'cifs' to 'vboxsf'
    Edit file 'C:\MIDEA\N4_VE11B_LATEST_20150530\n4\pkg\MrApplications\MrIDEA\VMAddons\mntview.sh':
        * 144: MountType=vboxsf
        * 225: options="" 
        * 224: mountSource=$shareName
    Add a 'SnapshotView' shared folder to VB mars machine pointing to 'C:\MIDEA\N4_VE11B_LATEST_20150530'. Edit 'C:\MIDEA\VM_VE11B\.VirtualBox\Machines\mars\mars.xml':
        * 53::
        
            <SharedFolders>
                <SharedFolder name="SnapshotView" hostPath="C:\MIDEA\N4_VE11B_LATEST_20150530" writable="true"/>
            </SharedFolders>

.. note::

    Execute the 'IDEA.Net' application and select scanner::

        sys
        select PRISMA-XR (3)




