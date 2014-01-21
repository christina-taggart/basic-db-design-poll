## Screenshot!

<a href="http://imgur.com/w9tSG6l"><img src="http://i.imgur.com/w9tSG6l.png?1" title="Hosted by imgur.com" /></a>

```xml

-- ---
-- Globals
-- ---

-- SET SQL_MODE="NO_AUTO_VALUE_ON_ZERO";
-- SET FOREIGN_KEY_CHECKS=0;

-- ---
-- Table 'users'
--
-- ---

DROP TABLE IF EXISTS `users`;

CREATE TABLE `users` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `name` CHAR NULL DEFAULT NULL,
  `political_party` CHAR NULL DEFAULT NULL,
  `age` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'authors'
--
-- ---

DROP TABLE IF EXISTS `authors`;

CREATE TABLE `authors` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `user_id` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'polls'
--
-- ---

DROP TABLE IF EXISTS `polls`;

CREATE TABLE `polls` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `question` CHAR NULL DEFAULT NULL,
  `author_id` INTEGER NULL DEFAULT NULL,
  `new field` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'responses'
--
-- ---

DROP TABLE IF EXISTS `responses`;

CREATE TABLE `responses` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `poll_id` INTEGER NULL DEFAULT NULL,
  `user_id` INTEGER NULL DEFAULT NULL,
  `response` CHAR NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Foreign Keys
-- ---

ALTER TABLE `authors` ADD FOREIGN KEY (user_id) REFERENCES `users` (`id`);
ALTER TABLE `polls` ADD FOREIGN KEY (author_id) REFERENCES `authors` (`id`);
ALTER TABLE `responses` ADD FOREIGN KEY (poll_id) REFERENCES `polls` (`id`);
ALTER TABLE `responses` ADD FOREIGN KEY (user_id) REFERENCES `users` (`id`);

-- ---
-- Table Properties
-- ---

-- ALTER TABLE `users` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `authors` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `polls` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `responses` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;

-- ---
-- Test Data
-- ---

-- INSERT INTO `users` (`id`,`name`,`political_party`,`age`) VALUES
-- ('','','','');
-- INSERT INTO `authors` (`id`,`user_id`) VALUES
-- ('','');
-- INSERT INTO `polls` (`id`,`question`,`author_id`,`new field`) VALUES
-- ('','','','');
-- INSERT INTO `responses` (`id`,`poll_id`,`user_id`,`response`) VALUES
-- ('','','','');
```