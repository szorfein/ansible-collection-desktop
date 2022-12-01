GPU Drivers
-----------

`dotfiles_gpu_driver` can support:

+ `intel_gen7` - ivy bridge, gen 7
+ `intel` - on recent Intel (Broadwell, Gen 8 and more)

If your gpu is not yet supported, you have to install it by hand as you are used to.

Intel Gen X
-----------

You have to check the output of `lspci -v` with VGA, e.g:

```output
00:02.0 VGA compatible controller: Intel Corporation Atom Processor Z36xxx/Z37xxx Series Graphics & Display (rev 0e) (prog-if 00 [VGA controller])
        DeviceName:  Onboard IGD
        Subsystem: CLEVO/KAPOK Computer Device XXXX
        ...
        Flags: bus master, fast devsel, latency 0, IRQ 94
        Capabilities: <access denied>
        Kernel driver in use: i915
        Kernel modules: i915
```

And compare to [intel gpu](https://en.wikipedia.org/wiki/Intel_Graphics_Technology), here the `Z36xxx/Z37xxx` is a `Gen 7` (Ivy Bridge), so the playbook will check and install `mesa` and `libva-intel-driver` for the hardware video acceleration.  

For a gen 8 (broadwell) and more recent, it will instead install `mesa` and `intel-media-driver`.

