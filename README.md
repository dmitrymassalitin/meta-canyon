# dmitrymassalitin
Description
We need to create a custom firmware image for the device based on the
VAR-SOM-MX8M-PLUS Evaluation Kit.
During this task the only goal is to copy the machine, u-boot board and
devicetree from the NXP/Variscite BSP with our own names. All these changes should
be provided as a separate meta-layer with our own manifest file uploaded to GitHub,
GitLab, Bitbucket or any other public git repository hosting.
Target hardware:
●​ SoM - VAR-SOM-MX8M-PLUS - link
●​ Development board - VAR-SOM-MX8M-PLUS Evaluation Kit - link
OS specification:
●​ Yocto Linux - Mickledore (kernel 6.6.23) - link
●​ Distro - fsl-imx-xwayland
●​ Machine - imx8mp-var-dart
●​ Image - fsl-image-gui
Tasks
1.​ Prepare build environment with 'repo' tool - link
2.​ Start Docker container.
3.​ Build original image
4.​ Create a new meta-layer named meta-canyon using bitbake-layers tool
5.​ Push sources of the meta-canyon layer to GitHub/GitLab/Bitbucket/…
6.​ Copy the manifest from Variscite to meta-canyon layer and modify it to
include the meta-canyon
7.​ Copy the configuration file of the machine imx8mp-var-dart the
meta-canyon and rename it to canyon-mx8mp
8.​ Modify the hostname of the board by adding the base-files_%.bbappend
with a dedicated variable.
9.​ Make copy of the imx8mp_var_dart board to canyon_mx8mp:
10.​ Make copy of the Linux kernel's devicetree:
11.​ Copy the fsl-image-gui image recipe to the meta-canyon layer and rename
it to canyon-fw-image.
12.​ Build the custom image:
○​ machine - canyon-mx8mp
○​ distro - fsl-imx-xwayland
○​ image - canyon-fw-image

Sstate summary: Wanted 127 Local 3 Mirrors 0 Missed 124 Current 6998 (2% match, 98% complete)##############          | ETA:  0:00:01
Removing 74 stale sstate objects for arch imx8mp_var_dart: 100% |####################################################| Time: 0:00:00
Removing 3 stale sstate objects for arch armv8a: 100% |##############################################################| Time: 0:00:00
NOTE: Executing Tasks
WARNING: kernel-module-isp-vvcam-4.2.2.24.2-r0 do_install: Module.symvers not found in /workdir/build_xwayland/tmp/work/imx8mp_var_dart-poky-linux/kernel-module-isp-vvcam/4.2.2.24.2/git/vvcam/v4l2/
WARNING: kernel-module-isp-vvcam-4.2.2.24.2-r0 do_install: Please consider setting MODULES_MODULE_SYMVERS_LOCATION to a
WARNING: kernel-module-isp-vvcam-4.2.2.24.2-r0 do_install: directory below B to get correct inter-module dependencies
WARNING: linux-variscite-6.6.23+git-r0 do_package_qa: QA Issue: File /usr/src/debug/linux-variscite/6.6.23+git/lib/oid_registry_data.c in package linux-variscite-src contains reference to TMPDIR
File /usr/src/debug/linux-variscite/6.6.23+git/drivers/tty/vt/consolemap_deftbl.c in package linux-variscite-src contains reference to TMPDIR
File /usr/src/debug/linux-variscite/6.6.23+git/drivers/video/logo/logo_linux_clut224.c in package linux-variscite-src contains reference to TMPDIR
File /usr/src/debug/linux-variscite/6.6.23+git/drivers/video/logo/logo_variscite_clut224.c in package linux-variscite-src contains reference to TMPDIR [buildpaths]
NOTE: Tasks Summary: Attempted 14163 tasks of which 14005 didn't need to be rerun and all succeeded.

Summary: There were 4 WARNING messages.