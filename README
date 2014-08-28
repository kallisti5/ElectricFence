Electric Fence 3.0
=========

Electric Fence is a different kind of malloc() debugger.

It uses the virtual memory hardware of your system to detect when
software overruns the boundaries of a malloc() buffer. It will also
detect any accesses of memory that has been released by free().
Because it uses the VM hardware for detection, Electric Fence stops
your program on the first instruction that causes a bounds violation.
It's then trivial to use a debugger to display the offending statement.

This version of Electric Fence should run on:
  - Linux kernel 1.1.83 or later
  - All System V Revision 4 platforms including:
    - Every known 386 System V
    - Solaris 2.x
    - SGI IRIX 5.0 or later
  - IBM AIX
  - Solaris 4.x or later (using an ANSI C compiler + static linking)
  - HP/UX 9.01 or later
  - OSF 1.3 (and possibly earlier versions) on a DECalpha
  - Haiku (and maybe BeOS)

Electric Fence will probably port to any ANSI/POSIX system that
provides mmap(), and mprotect(), as long as mprotect() has the
capability to turn off all access to a memory page, and mmap()
can use /dev/zero or the MAP_ANONYMOUS flag to create virtual
memory pages.

Build requirements
-----

The only real build requirement is a C compiler and the SCons build system.

[SCons] is a python based software construction tool that has been ported to
most platforms and is available in most Linux distribution repositories.

Build
-----
  - To compile
    - ```scons```
  - To clean
    - ```scons -c```

Usage
-----

Using Electric Fence is easy. You can use it multiple ways:

  - Link the generated static ```libefence.a``` archive into your application at build.
  - Preload the generated shared library ```libefence.so``` at runtime via the following:
    - Linux / Haiku / Solaris / HP-UX
      - ```LD_PRELOAD=./path/to/library/libefence.so  /bin/myapplication```
    - AIX 5.3+ (32-bit)
      - ```LDR_PRELOAD=./path/to/library/libefence.so  /bin/myapplication```
    - AIX 5.3+ (64-bit)
      - ```LDR_PRELOAD64=./path/to/library/libefence.so  /bin/myapplication```

Authors
-----

  - Alexander von Gluck IV <kallisti5@unixzen.com>
  - Bruce Perens <bruce@pixar.com>


Original Author
-----

Thanks go out to the original author Bruce Perens <Bruce@Pixar.com> for creating such a simple, yet powerful tool that is extremely useful to this day.

I chose to fork continuing the "Electric Fence" name as the project seems dead in the water developmentally. If any of the original authors want to reclaim this name, please reach out to me and I can rename this fork.

License
-----

Electric Fence is released under the GPLv2 license.

[SCons]:http://www.scons.org/
