CREATE TABLE Movies (
  movie_name VARCHAR(100) PRIMARY KEY,
  release_date DATE,
  duration INT,
  director VARCHAR(100),
  rating VARCHAR(10)
);

CREATE TABLE Actors (
  movie_name VARCHAR(100),
  actor_name VARCHAR(100),
  PRIMARY KEY (movie_name, actor_name),
  FOREIGN KEY (movie_name) REFERENCES Movies(movie_name)
);

CREATE TABLE Cinemas (
  cinema_name VARCHAR(100) PRIMARY KEY,
  address VARCHAR(100),
  phone_number VARCHAR(20)
);

CREATE TABLE Showing (
  movie_name VARCHAR(100),
  cinema_name VARCHAR(100),
  end_time DATE,
  PRIMARY KEY (movie_name, cinema_name),
  FOREIGN KEY (movie_name) REFERENCES Movies(movie_name),
  FOREIGN KEY (cinema_name) REFERENCES Cinemas(cinema_name)
);

CREATE TABLE Theaters (
  cinema_name VARCHAR(100),
  theater_number INT,
  PRIMARY KEY (cinema_name, theater_number),
  FOREIGN KEY (cinema_name) REFERENCES Cinemas(cinema_name)
);

CREATE TABLE Seats (
  cinema_name VARCHAR(100),
  theater_number INT,
  seat_number INT,
  seat_type VARCHAR(20),
  PRIMARY KEY (cinema_name, theater_number, seat_number),
  FOREIGN KEY (cinema_name, theater_number) REFERENCES Theaters(cinema_name, theater_number)
);

CREATE TABLE MovieSessions (
  session_id INT PRIMARY KEY,
  cinema_name VARCHAR(100),
  theater_number INT,
  movie_name VARCHAR(100),
  showtime DATETIME,
  FOREIGN KEY (cinema_name, theater_number) REFERENCES Theaters(cinema_name, theater_number),
  FOREIGN KEY (movie_name) REFERENCES Movies(movie_name)
);

CREATE TABLE TicketInfo (
  session_id INT,
  cinema_name VARCHAR(100),
  theater_number INT,
  seat_number INT,
  price DECIMAL(8,2),
  is_reserved INT,
  PRIMARY KEY (session_id, seat_number),
  FOREIGN KEY (session_id) REFERENCES MovieSessions(session_id),
  FOREIGN KEY (cinema_name, theater_number, seat_number) REFERENCES Seats(cinema_name, theater_number, seat_number)
);

CREATE TABLE Members (
  member_id INT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  phone_number VARCHAR(20)
);

CREATE TABLE Orders (
  order_id INT PRIMARY KEY,
  session_id INT,
  member_id INT,
  order_time DATETIME,
  FOREIGN KEY (session_id) REFERENCES MovieSessions(session_id),
  FOREIGN KEY (member_id) REFERENCES Members(member_id)
);

CREATE TABLE BookingSeats (
  order_id INT,
  cinema_name VARCHAR(100),
  theater_number INT,
  seat_number INT,
  PRIMARY KEY (order_id, seat_number),
  FOREIGN KEY (order_id) REFERENCES Orders(order_id),
  FOREIGN KEY (cinema_name, theater_number, seat_number) REFERENCES Seats(cinema_name, theater_number, seat_number)
);