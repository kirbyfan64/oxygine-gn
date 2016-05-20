Using Oxygine with GN
=====================

This repository holds some files related to using Oxygine with the GN build system.

Instructions
************

- **Make sure you have GN installed.**
- Run ``./setup`` to initialize the working directory.
- Generate and build: ``gn gen bld --args="..." && cd bld && ninja``.
- After building, you need to copy the contents of
  ``oxygine-framework/examples/HelloWorld/data`` to the build directory in order
  for the executable to run correctly.

Using it in your own project
****************************

The core files are ``oxygine/BUILD.gn`` and ``oxygine/config.gni``. In your own
``BUILDCONFIG.gn``, you should import ``//oxygine/config.gni`` like this project
does. Then, in your build targets, add the config ``//oxygine:oxygine``. Of course,
you need to adjust the paths in your own project.

Note the following:

- I had to clear the list of configurations (``configs = []``) in my executable
  target because I was getting weird linker errors.

- A sample ``args.gn`` is located in the main directory.

License
*******

The files in this directory are in the public domain. That way you can use them
easily in your own GN build scripts.

The contents of the submodule repos are (obviously) under their own licenses.
