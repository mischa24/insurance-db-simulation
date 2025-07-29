-- phpMyAdmin SQL Dump
-- version 5.2.1
-- https://www.phpmyadmin.net/
--
-- Εξυπηρετητής: 127.0.0.1
-- Χρόνος δημιουργίας: 21 Μαρ 2024 στις 19:19:25
-- Έκδοση διακομιστή: 10.4.32-MariaDB
-- Έκδοση PHP: 8.2.12

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Βάση δεδομένων: `insurance`
--

-- --------------------------------------------------------

--
-- Δομή πίνακα για τον πίνακα `car`
--

CREATE TABLE `car` (
  `car_id` mediumint(9) NOT NULL,
  `plate` varchar(40) NOT NULL,
  `price` mediumint(9) NOT NULL,
  `color` varchar(20) NOT NULL,
  `year` smallint(6) NOT NULL,
  `customer_id` mediumint(9) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Άδειασμα δεδομένων του πίνακα `car`
--

INSERT INTO `car` (`car_id`, `plate`, `price`, `color`, `year`, `customer_id`) VALUES
(1, 'ACB-2118', 14800, 'red', 2009, 1),
(2, 'ABC-2118', 15900, 'red', 2010, 2),
(4, 'ACB-2118', 14800, 'red', 2009, 1),
(5, 'ABC-2118', 15900, 'red', 2010, 2),
(7, 'ACB-2118', 14800, 'red', 2009, 1),
(8, 'ABC-2118', 15900, 'red', 2010, 2),
(10, 'ABC-2129', 12200, 'red', 2013, 7),
(11, 'ABC-2129', 12200, 'red', 2013, 7),
(12, 'ABC-2129', 12200, 'red', 2013, 7),
(13, 'ABC-2129', 12200, 'red', 2013, 7),
(14, 'ACB-2118', 14800, 'red', 2009, 1),
(15, 'ACB-2118', 14800, 'red', 2009, 1);

-- --------------------------------------------------------

--
-- Δομή πίνακα για τον πίνακα `customer`
--

CREATE TABLE `customer` (
  `customer_id` mediumint(9) NOT NULL,
  `first_name` varchar(40) NOT NULL,
  `last_name` varchar(40) NOT NULL,
  `age` tinyint(3) UNSIGNED DEFAULT NULL,
  `email` varchar(40) NOT NULL,
  `phone` varchar(40) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Άδειασμα δεδομένων του πίνακα `customer`
--

INSERT INTO `customer` (`customer_id`, `first_name`, `last_name`, `age`, `email`, `phone`) VALUES
(1, 'Dimitris', 'Dimitriou', 28, 'dimdim@irsmail.com', '21336884459'),
(2, 'Maria', 'Dimitriou', 29, 'mdim@irsmail.com', '21336884569'),
(3, 'Paraskevas', 'Konstantinidis', 58, 'kpa@jrsmail.com', '21336881234'),
(4, 'Sofia', 'Gramatopoulou', NULL, 'sgr@jrsmail.com', '21336353545'),
(5, 'Sofia', 'Gramatopoulou', NULL, 'sgr@jrsmail.com', '21336353545'),
(6, 'Geo', 'Dimitriou', 28, 'dimdim@jrsmail.com', '21336884459'),
(7, 'Sofia', 'Gramatopoulou', NULL, 'sgr@jrsmail.com', '21336353545'),
(8, 'Geo', 'Dimitriou', 28, 'dimdim@jrsmail.com', '21336884459'),
(9, 'Sofia', 'Gramatopoulou', NULL, 'sgr@jrsmail.com', '21336353545'),
(10, 'Geo', 'Dimitriou', 28, 'dimdim@jrsmail.com', '21336884459'),
(11, 'Kostas', 'Dimitriou', 23, 'kdim@jrsmail.com', '21336884425'),
(12, 'Sofia', 'Gramatopoulou', NULL, 'sgr@jrsmail.com', '21336353545'),
(13, 'Geo', 'Dimitriou', 28, 'dimdim@jrsmail.com', '21336884459'),
(14, 'Kostas', 'Dimitriou', 23, 'kdim@jrsmail.com', '21336884425'),
(15, 'Panos', 'Xaralampidis', 31, 'px@jrsmail.com', '21336884488'),
(16, 'Nasos', 'Xristou', 19, 'nx@jrsmail.com', '21336884411'),
(17, 'Nasos', 'Papapetrou', 25, 'np@jrsmail.com', '21336884422'),
(18, 'Takis', 'Papadopoulos', 25, 'tp@jrsmail.com', '21336884433');

--
-- Ευρετήρια για άχρηστους πίνακες
--

--
-- Ευρετήρια για πίνακα `car`
--
ALTER TABLE `car`
  ADD PRIMARY KEY (`car_id`),
  ADD KEY `customer_id` (`customer_id`);

--
-- Ευρετήρια για πίνακα `customer`
--
ALTER TABLE `customer`
  ADD PRIMARY KEY (`customer_id`);

--
-- AUTO_INCREMENT για άχρηστους πίνακες
--

--
-- AUTO_INCREMENT για πίνακα `car`
--
ALTER TABLE `car`
  MODIFY `car_id` mediumint(9) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=16;

--
-- AUTO_INCREMENT για πίνακα `customer`
--
ALTER TABLE `customer`
  MODIFY `customer_id` mediumint(9) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=19;

--
-- Περιορισμοί για άχρηστους πίνακες
--

--
-- Περιορισμοί για πίνακα `car`
--
ALTER TABLE `car`
  ADD CONSTRAINT `car_ibfk_1` FOREIGN KEY (`customer_id`) REFERENCES `customer` (`customer_id`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
