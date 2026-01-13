# Tetris-Game-SFML

I will be making a tetris game using the graphics library SFML (Simple and Fast Media Layer). This was made as a Semester Project.

### Note:
I used code from another git repository and modified it. The repository I cloned was: https://github.com/ThomasGITH/Tetris-SFML


### Modifications:
1. Added a section which shows the next piece that will come.
2. Improved rotation of blocks.
3. Added a Game Over fucntionality instead of the game just closing.
4. Changed Forwa font to Roboto.
5. Ability to change the size of the grid. The grid and the pieces will resize accordingly to fit the window size.
6. Pausing the game by pressing P.
7. A Proper Game Over.
8. The falling speed increases as you score more points.

### Game Picture:
![Tetris Game](readme_picture/image.png)

### How to run?
#### Prerequisites:
You need to have [Meson](https://mesonbuild.com/index.html), [Python](https://www.python.org/) and [pip](https://pypi.org/project/pip/) installed in your system. Meson is the build system which will help us compile the project properly. I am going to assume you already have Python and pip installed. You now need to install Meson.
```bash
pip install meson
```
#### Configuration:
```bash
# configures and makes the project build files inside the build directory
python -m meson setup build
```
#### Compilation:
```bash
# Compiles the project using the build files in the build directory
python -m meson compile -C build
```
This will produce the final Tetris executable in the _build_ directory.
#### Running the executable:
You can run the executable using the following commands:
```bash
#for linux
./build/Tetris

#for windows
.\build\Tetris.exe
```
Do note that the above commands were run from the project root directory.
#### Extra Details:
The _meson.build_ file tries to find whether the correct version of SFML is present in the system. If it finds it, it uses that. If it does not, it clones the SFML repo into the _subprojects_ directory and then builds it. The details of the fetch are present in the _sfml.wrap_ file located at the root of the _subprojects_ directory.
