CREATE TABLE movie (
	movie_id SERIAL PRIMARY KEY,
	title VARCHAR(100),
	media_type_id INTEGER REFERENCES media_type(media_type_id)
);

SELECT * FROM media_type

INSERT INTO movie
(title, media_type_id)
VALUES
('LION KING', 3);


SELECT * 
FROM movie;

ALTER TABLE movie
ADD column genre_id
INT REFERENCES genre(genre_id)

UPDATE movie
SET genre_id = 22
WHERE movie_id = 2;

SELECT * FROM movie

SELECT ar.name, al.title
FROM album al
JOIN artist ar ON ar.artist_id = al.artist_id;

SELECT * FROM genre

SELECT * FROM track
WHERE genre_id IN (
	SELECT genre_id FROM genre
  WHERE name IN ('Jazz', 'Blues')
);

SELECT * FROM customer
WHERE company IS NOT null

SELECT ar.artist_id, ar.name, COUNT(*)
FROM artist ar
JOIN album a ON ar.artist_id = a.artist_id
GROUP BY ar.artist_id
ORDER BY count DESC;

SELECT DISTINCT country FROM customer;