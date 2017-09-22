#!python 
# this script help compile builds
import platform
import os
import sys
import glob

from build_config import * #build configs
from build_support import * #build helper

print("Project Script Config!")
print("Current Dir: " + os.getcwd())
CURRENT_DIR = os.getcwd()

#get the mode flag from the command line
#default to 'release' if the user didn't specify
projectmode = ARGUMENTS.get('mode', 'release')   #holds current mode
osplatform = sys.platform

buildroot = './bin/' + projectmode			#holds the root of the build directory tree
targetpath = buildroot + '/' + projectname	#holds the path to the executable in the build directory

if osplatform == 'win32': #window tool default to vs2017
    env = Environment(ENV = os.environ, MSVC_USE_SCRIPT=VS_TOOL_BAT)
else:
    env = Environment(ENV = os.environ) #this load user complete external environment

Export('env','SRC_PATH','buildroot','include_packages','core_packages','CURRENT_DIR','SDL2_LIB_PATH','SDL2_INCLUDE_PATH','buildroot','targetpath','builddir','lib_packages')

# build path checks
target_dir = '#' + SelectBuildDir(build_base_dir)
SConscript(target_dir + os.sep + 'SConscript')







