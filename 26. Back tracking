% Facts about fruits and their colors
fruit_color(apple, red).
fruit_color(banana, yellow).
fruit_color(grape, purple).
fruit_color(orange, orange).
fruit_color(pear, green).

% Predicate to query the color of a fruit
color_of(Fruit, Color) :-
    fruit_color(Fruit, Color).

% Backtracking predicate to find fruits of a specific color
fruits_of_color(Color, Fruits) :-
    setof(Fruit, color_of(Fruit, Color), Fruits).

% Backtracking predicate to find colors of a specific fruit
colors_of_fruit(Fruit, Colors) :-
    setof(Color, color_of(Fruit, Color), Colors).
