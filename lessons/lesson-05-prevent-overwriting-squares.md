## Prevent Players from Overwriting Squares

As of now, if a player clicks on a square that's already been played on, they can still re-play on that square. Let's prevent that from happening.
```
state = {
    squares: {
        1: { content: '', played: false },
        2: { content: '', played: false },
        3: { content: '', played: false },
        4: { content: '', played: false },
        5: { content: '', played: false },
        6: { content: '', played: false },
        7: { content: '', played: false },
        8: { content: '', played: false },
        9: { content: '', played: false },
    },
    isPlayerOnesTurn: true,
}
```

```
handleSquareClick = (e) => {
    const clickedSquareId = e.target.id;

    // if the square has already been used, don't do anything
    if (this.state.squares[clickedSquareId].played) {
        return;
    }

    const letterToAdd = this.state.isPlayerOnesTurn ? 'x' : 'o';

    this.setState({
        isPlayerOnesTurn: !this.state.isPlayerOnesTurn,
        squares: {
            ...this.state.squares,
            [clickedSquareId]: { content: letterToAdd, played: true }
        },
    });
}
```

[Continue to the next lesson](lesson-06-assigning-squares-to-players.md)
