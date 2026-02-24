# 1. Objects to build
obj-y += kernel/ksu.o
obj-y += allowlist.o
obj-y += apk_sign.o
obj-y += app_profile.o
obj-y += extras.o
obj-y += feature.o
obj-y += file_wrapper.o
obj-y += kernel_compat.o
obj-y += kernel_umount.o
obj-y += ksud.o
obj-y += lsm_hooks.o
obj-y += seccomp_cache.o
obj-y += setuid_hook.o
obj-y += su_mount_ns.o
obj-y += sucompat.o
obj-y += supercalls.o
obj-y += throne_tracker.o
obj-y += tiny_sulog.o
obj-y += util.o

# Build the selinux files from the subfolder
obj-y += selinux/rules.o
obj-y += selinux/selinux.o
obj-y += selinux/sepolicy.o

# 2. Fix the flask.h and include paths
# This tells the compiler where to find the kernel's own SELinux headers
ccflags-y += -I$(srctree)/security/selinux/include
ccflags-y += -I$(srctree)/$(src)/kernel
ccflags-y += -I$(srctree)/$(src)/selinux

# 3. Critical Flags
ccflags-y += -DCONFIG_KSU_NEXT_MANUAL_HOOK
ccflags-y += -Wno-strict-prototypes -Wno-implicit-function-declaration

# 4. THE V2 SIGNATURE (The Handshake)
# Hardcoding these prevents shell escaping issues in the .yml
KSU_EXPECTED_SIZE := 0x3e6
KSU_EXPECTED_HASH := 79e590113c4c4c0c222978e413a5faa801666957b1212a328e46c00c69821bf7

ccflags-y += -DKSU_NEXT_EXPECTED_SIZE=$(KSU_EXPECTED_SIZE)
ccflags-y += -DKSU_NEXT_EXPECTED_HASH=\"$(KSU_EXPECTED_HASH)\"
