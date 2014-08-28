import os
import sys
import platform
env = Environment(ENV = os.environ)

env["CC"] = os.getenv("CC") or env["CC"]
env["CXX"] = os.getenv("CXX") or env["CXX"]
env["ENV"].update(x for x in os.environ.items() if x[0].startswith("CCC_"))

env.Append(CPPPATH = ['#src'])
env.Append(LIBPATH = ['#src'])
env.Append(CFLAGS = ['-g'])

if platform == 'HP-UX':
  env.Append(CFLAGS = ['-Aa', '-D_HPUX_SOURCE', '-DPAGE_PROTECTION_VIOLATED_SIGNAL=SIGBUS'])
elif platform == 'AIX':
  # COMPILE THE PROGRAMS YOU ARE DEBUGGING WITH THESE FLAGS, TOO.
  env.Append(CFLAGS = ['-bnso', '-bnodelcsect', '-bI:/lib/syscalls.exp'])
elif platform == 'Solaris':
  # Note the definition of PAGE_PROTECTION_VIOLATED_SIGNAL. This may vary
  # depend on what version of Sun hardware you have.
  # You'll probably have to link the program you are debugging with -Bstatic
  # as well if using Sun's compiler, -static if using GCC.
  env.Append(CFLAGS = ['-Bstatic', '-DPAGE_PROTECTION_VIOLATED_SIGNAL=SIGBUS'])

Export("env")

# Main library
SConscript("#src/SConscript")

# Unit tests
SConscript("#tests/SConscript")
