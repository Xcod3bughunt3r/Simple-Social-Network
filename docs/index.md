<p align="center"><a href="https://www.itsecurity.id/"><img height="150" title="Xcod3bughunt3r" src="/images/face.png"/></a></p>

<div align="center">
	<h1> Simple Social Network </h1>
</div>

#### *[Fav Quote](http://fav-quote.byethost17.com)* `is a Micro Social Network developed in PHP, MySQL (PDO_MYSQL Controller for the connection), Bootstrap 3 and Vue.JS 2. This project don't use classes or a php framework. To validate the login forms uses the` *[validator for bootstrap](http://1000hz.github.io/bootstrap-validator/)*

<a name="started"></a>
### `Getting Started`
#### ``This page will help you get started with Fav Quote (Simple Social Network).``

<a name="requirements"></a>
### `Requirements`
  * `PHP 5.6`
  * `MySQL or MariaDB`
  * `Apache Server`

<a name="installation"></a>
### `Installation`
#### `Create a database. Run the following SQL script.`
```SQL
-- -----------------------------------------------------
-- Schema NETWORK
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `NETWORK` DEFAULT CHARACTER SET utf8 ;
USE `NETWORK` ;

-- -----------------------------------------------------
-- Table `NETWORK`.`COUNTRIES`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `NETWORK`.`COUNTRIES` (
  `ID_COUNTRY` INT UNSIGNED NOT NULL AUTO_INCREMENT,
  `ISO` VARCHAR(2) NOT NULL,
  `COUNTRY` VARCHAR(80) NOT NULL,
  PRIMARY KEY (`ID_COUNTRY`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `NETWORK`.`USERS`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `NETWORK`.`USERS` (
  `ID_USER` INT UNSIGNED NOT NULL AUTO_INCREMENT,
  `GUID` VARCHAR(20) NOT NULL,
  `USERNAME` VARCHAR(20) NOT NULL,
  `PASSWORD` VARCHAR(255) NOT NULL,
  `CREATED_AT` DATE NOT NULL,
  `ID_COUNTRY` INT UNSIGNED NOT NULL,
  PRIMARY KEY (`ID_USER`),
  UNIQUE INDEX `ID_USER_UNIQUE` (`ID_USER` ASC),
  UNIQUE INDEX `USER_UNIQUE` (`USERNAME` ASC),
  UNIQUE INDEX `GUID_UNIQUE` (`GUID` ASC),
  INDEX `fk_USERS_COUNTRIES1_idx` (`ID_COUNTRY` ASC),
  CONSTRAINT `fk_USERS_COUNTRIES1`
    FOREIGN KEY (`ID_COUNTRY`)
    REFERENCES `NETWORK`.`COUNTRIES` (`ID_COUNTRY`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `NETWORK`.`QUOTES`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `NETWORK`.`QUOTES` (
  `ID_QUOTE` INT UNSIGNED NOT NULL AUTO_INCREMENT,
  `QUOTE` VARCHAR(120) NOT NULL,
  `POST_DATE` DATE NOT NULL,
  `POST_TIME` TIME NOT NULL,
  `LIKES` INT UNSIGNED NOT NULL DEFAULT 0,
  `ID_USER` INT UNSIGNED NOT NULL,
  PRIMARY KEY (`ID_QUOTE`),
  UNIQUE INDEX `ID_QUOTE_UNIQUE` (`ID_QUOTE` ASC),
  INDEX `fk_QUOTES_USERS_idx` (`ID_USER` ASC),
  CONSTRAINT `fk_QUOTES_USERS`
    FOREIGN KEY (`ID_USER`)
    REFERENCES `NETWORK`.`USERS` (`ID_USER`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `NETWORK`.`LIKES`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `NETWORK`.`LIKES` (
  `ID_USER` INT UNSIGNED NOT NULL,
  `ID_QUOTE` INT UNSIGNED NOT NULL,
  PRIMARY KEY (`ID_USER`, `ID_QUOTE`),
  INDEX `fk_LIKES_QUOTES1_idx` (`ID_QUOTE` ASC),
  CONSTRAINT `fk_LIKES_USERS1`
    FOREIGN KEY (`ID_USER`)
    REFERENCES `NETWORK`.`USERS` (`ID_USER`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_LIKES_QUOTES1`
    FOREIGN KEY (`ID_QUOTE`)
    REFERENCES `NETWORK`.`QUOTES` (`ID_QUOTE`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;
```

#### `Create a project`
  1. `Clone or Download this repository`
  2. `Unzip the archive if needed`
  3. `Copy the folder in the htdocs dir`
  4. `Start a Text Editor (Atom, Sublime, Visual Studio Code, Vim, etc)`
  5. `Add the project folder to the editor`

<div align="center">
	<h3> Database Schema </h3>
	<a href="#installation">
		<img src="https://raw.githubusercontent.com/Xcod3bughunt3r/Simple-Social-Network/master/docs/images/schema.png" alt="schema">
	</a>
</div>

<a name="built"></a>
### `Built With`
  * `XAMPP for Windows 5.6.32` (*[XAMPP](https://www.apachefriends.org/download.html)*)
  * `Visual Studio Code` (*[VSCode](https://code.visualstudio.com/)*)

<a name="testing"></a>
### `Running the testing`
#### `You can test a demo websites` *[here](http://fav-quote.byethost17.com).*

<a name="changelog"></a>
### `Changelog`
#### `1.0.6 (08/15/2022)`
````
  * <table border="0" cellpadding="4">
		<tr>
			<td>
				<strong>Language:</strong>
			</td>
			<td>
				HTML, PHP, JavaScript
			</td>
		</tr>
		<tr>
			<td><strong>
				Requirements:
			</strong></td>
			<td>
				<ul>
					<li>
						PHP 5.6
					</li>
					<li>
						MySQL or MariaDB 
					</li>
					<li>
						Apache Server
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td><strong>
				Features:
			</strong></td>
			<td>
				<ul>
					<li>
						<a href="https://getbootstrap.com/docs/3.3/getting-started/">Bootstrap 3</a>
					</li>
					<li>
						<a href="http://1000hz.github.io/bootstrap-validator/">Validator for Bootstrap 3</a>
					</li>
					<li>
						<a href="https://vuejs.org/v2/guide/installation.html">Vue.JS 2</a>
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Changes:</strong>
			</td>
			<td>
				<ul>
					<li>
						Pagination in Vue.js
					</li>
				</ul>
			</td>
		</tr>
	</table>
````

#### `1.0.5 (06/15/2019)`
````
  * <table border="0" cellpadding="4">
		<tr>
			<td>
				<strong>Language:</strong>
			</td>
			<td>
				HTML, PHP, JavaScript
			</td>
		</tr>
		<tr>
			<td><strong>
				Requirements:
			</strong></td>
			<td>
				<ul>
					<li>
						PHP 5.6
					</li>
					<li>
						MySQL or MariaDB 
					</li>
					<li>
						Apache Server
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td><strong>
				Features:
			</strong></td>
			<td>
				<ul>
					<li>
						<a href="https://getbootstrap.com/docs/3.3/getting-started/">Bootstrap 3</a>
					</li>
					<li>
						<a href="http://1000hz.github.io/bootstrap-validator/">Validator for Bootstrap 3</a>
					</li>
					<li>
						<a href="https://vuejs.org/v2/guide/installation.html">Vue.JS 2</a>
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Changes:</strong>
			</td>
			<td>
				<ul>
					<li>
						Friendly URLs
					</li>
				</ul>
			</td>
		</tr>
	</table>
````

#### `1.0.4 (03/10/2019)`
````
  * <table border="0" cellpadding="4">
		<tr>
			<td>
				<strong>Language:</strong>
			</td>
			<td>
				HTML, PHP, JavaScript
			</td>
		</tr>
		<tr>
			<td><strong>
				Requirements:
			</strong></td>
			<td>
				<ul>
					<li>
						PHP 5.6
					</li>
					<li>
						MySQL or MariaDB 
					</li>
					<li>
						Apache Server
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td><strong>
				Features:
			</strong></td>
			<td>
				<ul>
					<li>
						<a href="https://getbootstrap.com/docs/3.3/getting-started/">Bootstrap 3</a>
					</li>
					<li>
						<a href="http://1000hz.github.io/bootstrap-validator/">Validator for Bootstrap 3</a>
					</li>
					<li>
						<a href="https://vuejs.org/v2/guide/installation.html">Vue.JS 2</a>
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Changes:</strong>
			</td>
			<td>
				<ul>
					<li>
						Show user for likes
					</li>
					<li>
						Check the unlike process
					</li>
				</ul>
			</td>
		</tr>
	</table>
````

#### `1.0.3 (01/18/2019)`
````
  * <table border="0" cellpadding="4">
		<tr>
			<td>
				<strong>Language:</strong>
			</td>
			<td>
				HTML, PHP, JavaScript
			</td>
		</tr>
		<tr>
			<td><strong>
				Requirements:
			</strong></td>
			<td>
				<ul>
					<li>
						PHP 5.6
					</li>
					<li>
						MySQL or MariaDB 
					</li>
					<li>
						Apache Server
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td><strong>
				Features:
			</strong></td>
			<td>
				<ul>
					<li>
						<a href="https://getbootstrap.com/docs/3.3/getting-started/">Bootstrap 3</a>
					</li>
					<li>
						<a href="http://1000hz.github.io/bootstrap-validator/">Validator for Bootstrap 3</a>
					</li>
					<li>
						<a href="https://vuejs.org/v2/guide/installation.html">Vue.JS 2</a>
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Changes:</strong>
			</td>
			<td>
				<ul>
					<li>
						Add a new table in database to save likes
					</li>
					<li>
						Add the profile page
					</li>
					<li>
						Add the location for the persons
					</li>
				</ul>
			</td>
		</tr>
	</table>
````

#### 1.0.2 (02/04/2018)
````
  * <table border="0" cellpadding="4">
		<tr>
			<td>
				<strong>Language:</strong>
			</td>
			<td>
				HTML, PHP, JavaScript
			</td>
		</tr>
		<tr>
			<td><strong>
				Requirements:
			</strong></td>
			<td>
				<ul>
					<li>
						PHP 5.6
					</li>
					<li>
						MySQL or MariaDB 
					</li>
					<li>
						Apache Server
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td><strong>
				Features:
			</strong></td>
			<td>
				<ul>
					<li>
						<a href="https://getbootstrap.com/docs/3.3/getting-started/">Bootstrap 3</a>
					</li>
					<li>
						<a href="http://1000hz.github.io/bootstrap-validator/">Validator for Bootstrap 3</a>
					</li>
					<li>
						<a href="https://vuejs.org/v2/guide/installation.html">Vue.JS 2</a>
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Changes:</strong>
			</td>
			<td>
				<ul>
					<li>
						Implementation of CDN
					</li>
					<li>
						Logout verification
					</li>
				</ul>
			</td>
		</tr>
	</table>
````

### `1.0.1 (12/02/2017)`
````
  * <table border="0" cellpadding="4">
		<tr>
			<td>
				<strong>Language:</strong>
			</td>
			<td>
				HTML, PHP, JavaScript
			</td>
		</tr>
		<tr>
			<td><strong>
				Requirements:
			</strong></td>
			<td>
				<ul>
					<li>
						PHP 5.6
					</li>
					<li>
						MySQL or MariaDB 
					</li>
					<li>
						Apache Server
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td><strong>
				Features:
			</strong></td>
			<td>
				<ul>
					<li>
						<a href="https://getbootstrap.com/docs/3.3/getting-started/">Bootstrap 3</a>
					</li>
					<li>
						<a href="http://1000hz.github.io/bootstrap-validator/">Validator for Bootstrap 3</a>
					</li>
					<li>
						<a href="https://vuejs.org/v2/guide/installation.html">Vue.JS 2</a>
					</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Changes:</strong>
			</td>
			<td>
				<ul>
					<li>
						Add validator for Bootstrap
					</li>
					<li>
						Add terms of service
					</li>
				</ul>
			</td>
		</tr>
	</table>
````

<a name="authors"></a>
### `Authors`
  * **ALIF FUSOBAR** - *Owner* - *[Xcod3bughunt3r](https://github.com/Xcod3bughunt3r)*
  * `See also the list of` *[contributors](https://github.com/Xcod3bughunt3r/Simple-Social-Network/contributors)* `who participated in this project.`

<a name="license"></a>
### `License`
#### `Fav Quote is licensed under the MIT License - see the` *[MIT License](https://opensource.org/licenses/MIT)* `for details.`
