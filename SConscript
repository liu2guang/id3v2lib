import os
from building import * 

# get current dir path
cwd = GetCurrentDir()

# init src and inc vars
src = []
inc = []

inc = inc + [cwd + "/include"]
inc = inc + [cwd + "/include/id3v2lib"]
src = src + Glob('./id3v2lib/src/*.c') 

# add group to IDE project
objs = DefineGroup('id3v2lib-1.0.0', src, depend = ['PKG_USING_ID3V2LIB'], CPPPATH = inc)

# traversal subscript
list = os.listdir(cwd)
if GetDepend('PKG_USING_ID3V2LIB'):
    for d in list:
        path = os.path.join(cwd, d)
        if os.path.isfile(os.path.join(path, 'SConscript')):
            objs = objs + SConscript(os.path.join(d, 'SConscript'))

Return('objs') 
