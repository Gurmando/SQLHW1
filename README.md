# SQLHW1


Add two more movies of your choosing to the table.

  
    Insert into Movies Values ('We Be Ballin', '69', 'Romance', 5.0, 'R');
    Insert into Movies Values ('We Are Not Ballin', '96', 'Horror', 5.0, 'PG');
  

Create a query to find all movies in the Sci-Fi genre.


    Select * From Movies Where Genre = 'Sci-fi';


Create a query to find all films that scored at least a 6.5 on IMDB


    Select * From Movies Where IMBD_Score >= 6.5;



For parents who have young kids, but who don't want to sit through long children's movies, create a query to find all of the movies rated G or PG that are less than 100 minutes long.


    Select * From Movies Where (Rating = 'G' OR Rating = 'PG') AND runtime < 100;


Create a query to show the average runtimes of movies scoring below a 7.5 on imdb, grouped by their respective genres.


    Select Genre, AVG(Runtime) From Movies Where IMDB_Score < 7.5 Group by Genre;


There's been a data entry mistake; Starship Troopers is actually rated R, not PG-13. Create a query that finds the movie by its title and changes its rating to R.



    Update Movies Set Rating = 'R' Where Title = 'Starship Troopers';



Show the ID number and rating of all of the Horror and Documentary movies in the database. Do this in only one query.



    Select Title, Rating From Movies Where Genre IN ('Horror', "Documentary");



This time let's find the average, maximum, and minimum IMDB score for movies of each rating.


    Select AVG(IMDB_Score), Max(IMDB_Score), Min(IMDB_Score) From Movies Group By Rating


That last query isn't very informative for ratings that only have 1 entry. Use a HAVING COUNT(*) > 1 clause to only show ratings with multiple movies showing.


    Select AVG(IMDB_Score), Max(IMDB_Score), Min(IMDB_Score) From Movies Group By Rating Having Count(*) > 1;


Make the movie list more child-friendly. Delete all entries that have a rating of R. Remember to record your queries in a README.md file


    Delete From Movies Where Genre = 'R'



Delete the Movies Table


    Drop table Movies


Delete the Database

    
    Drop database Theatre;







