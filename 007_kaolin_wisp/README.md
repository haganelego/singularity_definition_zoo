# Get some problem to run interactive app  
If you get the following error, add `__NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia` before run-command.
```
RuntimeError: make_default_context() wasn't able to create a context on any of the 1 detected devices
```