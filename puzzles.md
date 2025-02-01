# Simon Tatham's Portable Puzzle Collection

A collection of small one-player puzzle games.
<https://www.chiark.greenend.org.uk/~sgtatham/puzzles/>

```bash
dnf install puzzles
```


## Good puzzles

### Bridges (puzzle-bridges)
Connect all the islands with a network of bridges.  All islands must be
connected to a single bridge network.

### Filling (puzzle-filling)
Mark every square with the area of its containing region.

### Galaxies (puzzle-galaxies)
Divide the grid into rotationally symmetric regions each centred on a dot.

### Lightup (puzzle-lightup)
Place bulbs to light up all the squares.

### Loopy (puzzle-loopy)
Also known as *Slitherlink* or *Takegaki*.  Draw a single closed loop, given
clues about number of adjacent edges.

### Magnets (puzzle-magnets)
Place magnets to satisfy the clues and avoid like poles touching.

### Mines (puzzle-mines)
Basically *Minesweeper*.  Find all the mines without treading on any of them.

### Rectangles (puzzle-rect)
Divide the grid into rectangles with areas equal to the numbers.  Similar to
*Filling*?

### Slant (puzzle-slant)
Draw a maze of slanting lines that matches the clues.

### Unequal (puzzle-unequal)
Complete the latin square in accordance with the less than/greater than signs.


## Meh puzzles

### Blackbox (puzzle-blackbox)
Find the hidden balls in the box by bouncing laser beams off them.

H means obstacle - light goes directly onto a ball.  R means light is reflected
back.  E.g.:

           R 
        +-+-+-+
      R | | | |
        +-+-+-+
      H |O| |O|
        +-+-+-+
      R | | | |
        +-+-+-+

### Dominosa (puzzle-dominosa)
Tile the rectangle with a full set of dominoes.

### Keen (puzzle-keen)
Complete the latin square in accordance with the arithmetic clues.

### Map (puzzle-map)
Colour the map so that adjacent regions are never the same colour.

### Pattern (puzzle-pattern)
Fill in the pattern in the grid, given only the lengths of runs of black squares.

### Range (puzzle-range)
Place black squares to limit the visible distance from each numbered cell.

### Signpost (puzzle-signpost)
Connect the squares into a path following the arrows.

### Singles (puzzle-singles)
Black out the right set of duplicate numbers.

### Tents (puzzle-tents)
Place a tent next to each tree.

### Towers (puzzle-towers)
Complete the latin square of towers in accordance with the clues.


## Other puzzles

### Cube (puzzle-cube)
Pick up all the blue squares by rolling the cube over them.

### Fifteen (puzzle-fifteen)
Slide the tiles around to arrange them into order.

### Flip (puzzle-flip)
Basically *Lights Out*.  Flip groups of squares to light them all up at once.

### Guess (puzzle-guess)
Basically *Mastermind*.  Guess the hidden combination of colours.

### Inertia (puzzle-inertia)
Collect all the gems without running into any of the mines.

### Net (puzzle-net)
Rotate each tile to reassemble the network.  Similar to *Netslide*.

### Netslide (puzzle-netslide)
Slide a row at a time to reassemble the network.  Similar to *Net*.

### Pegs (puzzle-pegs)
Basically *Peg Solitaire*.  Jump pegs over each other to remove all but one.

### Samegame (puzzle-samegame)
Similar to *Bejeweled*.  Clear the grid by removing touching groups of the same colour squares.

### Sixteen (puzzle-sixteen)
Slide a row at a time to arrange the tiles into order.  Similar to *Fifteen*.

### Solo (puzzle-solo)
Basically *Sudoku*.  Fill in the grid so that each row, column and square block
contains one of every digit.

### Twiddle (puzzle-twiddle)
Rotate the tiles around themselves to arrange them into order.  Similar to
*Fifteen*.

### Untangle (puzzle-untangle)
Fill in the black and white grid to avoid runs of three.
