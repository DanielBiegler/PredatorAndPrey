# PREDATOR AND PREY CELLULAR AUTOMATON

The world is grid of cells, with 3 possibilities: Predator(Red), Prey(Green), or Empty(Black).

Both predator and prey have a set health, that changes over time.

The simulation works in steps, with the following rules:

    -For prey:
        -Tries to move in a random direction.
        -Health increases.
        -When health reaches a threshold:
            -They will reproduce, creating a new "Prey"
            -Their health resets to 1

    -For predator:
        -Tries to move in a random direction.
        -Health decreases.
        -When health reaches 0, they die and turn into "Nothing".
        -If the adjacent square is a prey:
            -They will eat it, turning it into a "predator" (reproducing)
            -Their health will increase by the amount of health the eaten prey had
            
           
 ![Image](http://i.imgur.com/ufXdrSz.png)

# HOW TO RUN THIS PROJECT
1. Build SFML
    https://www.sfml-dev.org/tutorials/2.4/compile-with-cmake.php
2. Build this project
    * **-g** for debug info, 
    * **-o** for output file: **PredatorAndPrey**, 
    * **-I** for Include path, 
    * **-l** for linker specific data,
    * **-L** for linker specific libraries
    * and the rest of the .cpp files to compile.
    `g++ -g -o PredatorAndPrey -ISFML/include Source/Application.cpp Source/Creature.cpp Source/Random.cpp main.cpp -lsfml-graphics -lsfml-window -lsfml-system -L<PATH_TO_BUILT_SFML>/lib`
3. Set SFML environment variable
    If SFML is not installed in a standard path, you need to tell the dynamic linker where to find the SFML libraries first by specifying LD_LIBRARY_PATH:
    `export LD_LIBRARY_PATH=<PATH_TO_THIS_PROJECT>/<PATH_TO_BUILT_SFML>/lib`
3. Link SFML statically if you dont want the environment variable
4. Run this project
    `<PATH_TO_THIS_PROJECT>/PredatorAndPrey`