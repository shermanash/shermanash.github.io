---
published: false
---

## Predicting Movie Metrics

For our second project, we were instructed to use linear regression to investigate predictions relating to the movie industry.  My initial idea centered around trying to predict the quality of a movie.  In a sense, predicting the imdb rating or metacritic score of a movie isn't entirely useful, as those ratings will nearly always be available as soon as the movie is released, but I wanted to see how far in advance we could guess.  

My initial idea was to use career averages for all the major players involved - director, writer, and cast, to see if there was a correlation between their previous body of work and their upcoming films.  So, if it was someone's third film, their "score" would be the average imdbrating of their first two films, if it was their 10th, I used the average of their first 9.  I gave some thought to weighting recent films higher than older ones, as its possible they would have more relevance to the quality of the next film produced, but ultimately decided to stick with the unweighted career average.  

This presented a problem when training the model, because if this was the first film for any of the major players, they didn't have an average score and I couldn't use them to train the model.  One way around this would have been to use a scoring system instead of a mean- for example, all directors would start at 0, and each time they create a top rated movie, they would get, say 5 points, while a below average movie would cause them to lose 5 points, and an average movie would leave their score unchanged.  

A better solution, which I unfortunately did not have time to implement, would be to train multiple regression models- one to predict the imdb rating of a movie, and another to predict the imdbrating of the director, given the ratings of the other actors and writer.  Similar models could be made for all inputs, so that if we wanted to predict the rating of a movie directed by Martin Scorcese, starring Brad Pitt, Matt Damon, and Andrew Sherman-Ash, we would first estimate Sherman-Ash's imdb rating, 


