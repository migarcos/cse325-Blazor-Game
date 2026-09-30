# Build a Connect Four game with Blazor
In this game, two players alternate taking turns placing a game piece (typically a checker) in the top of the board. Game pieces fall to the lowest row of a column and the player that places four game pieces to make a line horizontally, vertically, or diagonally wins.

**Skills learned**:

- Created a component
- Added that component to our home page
- Used dependency injection to manage the state of a game
- Made the game interactive with event handlers to place pieces and reset the game
- Wrote an error handler to report the state of the game
- Added parameters to our component

## Set Up

Create a new Blazor APP

    dotnet new blazor -n ConnectFour -f net10.0
    cd ConnectFour
    dotnet run
    Ctrl+Shift+P → .NET: Generate Assets for Build and Debug

## Project Structure vs Namespaces

     ConnectFour/                → namespace ConnectFour
    │
    ├── Program.cs              → usually in root, uses ConnectFour + ConnectFour.Components
    ├── GameState.cs            → namespace ConnectFour
    │
    └── Components/             → namespace ConnectFour.Components
        ├── App.razor
        ├── MainLayout.razor
        └── Board.razor

Namespace Mapping

    Folder / File Path	            Suggested Namespace	                Example Usage in Program.cs
    ConnectFour/GameState.cs	    namespace ConnectFour;	            using ConnectFour;
    ConnectFour/Components/	        namespace ConnectFour.Components;	using ConnectFour.Components;

- Root folder files (like GameState.cs) should use the base namespace (ConnectFour).

- Subfolders (like Components/) should extend the namespace (ConnectFour.Components).

- In Program.cs, you must using the correct namespace for each class you register with DI

### Util Sites

- [Learn Blazor](https://learn.microsoft.com/en-us/training/modules/dotnet-connect-four/)