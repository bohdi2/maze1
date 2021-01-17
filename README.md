# maze1

Programming exercise.

We want to have a maze with four rooms: a gold room, a silver room, a bronze room,
and a wood room. The only difference between the rooms are their names and their
connections to other rooms.

Within the maze the rooms are arranged in a grid like this:

    Gold   | Silver
    -------+--------
    Bronze |  Wood

Rooms are connected by doors which can be on the north, east, south, and west walls of a room. 
The gold room has doors to the east and south, the Silver room has doors to the west and south, and so
on. 

One of the rooms is the "current" room. You start in the gold room. 
You may move from one room to another by
moving north, east, south, or west. When you move to another room that room becomes
the current room.

## Implementation So Far

### Rooms
A room object needs to implement the `Room` interface.

There is one room defined: `GoldRoom`. You need to add the other three rooms.

### Maze and MazeFactory

A `Maze` contains `Rooms` and has methods to get the current room and to move in the four directions.
Currently the move methods do nothing. You're always in the gold room. You need to modify
the move methods to do the right thing. This is the hard part of the exercise. 

It may not be apparent now but creating the `Maze` object will become complicated as
we add more rooms and features. The `MazeFactory` is in charge of creating a `Maze`.
You may need to work on `MazeFactory.create()` to wire everything together, although
you can also hard code things in `Maze`.

### MazeTest

For now we run the program using the Junit test class `MazeTest`. Here is the most important
test which has us move clockwise through the four rooms.

    @Test
    public void testAllRooms() {
        maze.moveEast();
        assertEquals("Siver", maze.getCurrentRoom().getName());

        maze.moveSouth();
        assertEquals("Wood", maze.getCurrentRoom().getName());

        maze.moveWest();
        assertEquals("Bronze", maze.getCurrentRoom().getName());

        maze.moveNorth();
        assertEquals("Gold", maze.getCurrentRoom().getName());
    }

When you run `mvn clean test` this test method will fail.

You need to modify the `Maze` class to make all the tests work. Feel free to add 
additional tests.
