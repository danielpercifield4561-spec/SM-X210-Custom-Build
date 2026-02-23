# Kbuild Makefile for in-tree KernelSU-Next-Legacy integration
obj-$(CONFIG_KSU) += kernelsu.o

# Combine all the .c files into one object named kernelsu.o
kernelsu-objs := ksu.o \
                 allowlist.o \
                 apk_sign.o \
                 app_profile.o \
                 extras.o \
                 feature.o \
                 file_wrapper.o \
                 kernel_compat.o \
                 kernel_umount.o \
                 ksud.o \
                 lsm_hooks.o \
                 pkg_observer.o \
                 seccomp_cache.o \
                 setuid_hook.o \
                 su_mount_ns.o \
                 sucompat.o \
                 supercalls.o \
                 syscall_hook_manager.o \
                 throne_tracker.o \
                 tiny_sulog.o \
                 util.o \
                 selinux/rules.o \
                 selinux/selinux.o \
                 selinux/sepolicy.o

# If your kernel is version 5.10+, you might need the symbols checker for kprobes
# This is usually optional for manual hook builds
# obj-y += tools/check_symbols.o

# Ensure the compiler can find your .h files in the subfolders
ccflags-y += -I$(src) -I$(src)/selinux
