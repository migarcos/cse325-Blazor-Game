# Build a Connect Four game with Blazor


## Set Up

Create a new Blazor APP

    dotnet new blazor -n ConnectFourGame -f net10.0
    cd ConnectFourGame
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