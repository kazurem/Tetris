project('Tetris', 'cpp')
srcs = ['main.cpp']

# SFML CONFIGURATION
sfml_version = '2.6.1'
sfml_targets = ['sfml-window', 'sfml-graphics', 'sfml-system']

deps = []

# Find SFML in system 
system_sfml_found = true
foreach sfml_target : sfml_targets
  dep = dependency(sfml_target, version : sfml_version, required : false)
  if not dep.found()
    system_sfml_found = false
    break
  endif
  deps += [dep]  
endforeach

# Fetch SFML and build it as a subproject in case SFML isn't found in the system
# All the details about the fetch are in subprojects/sfml.wrap file.
if not system_sfml_found
  sfml_proj = subproject('sfml')
  deps = sfml_proj.get_variable('sfml_dep') 
endif

executable('Tetris', sources : srcs, dependencies : deps)
