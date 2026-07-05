-- MySQL dump 10.16  Distrib 10.1.48-MariaDB, for Win64 (AMD64)
--
-- Host: localhost    Database: db_0921
-- ------------------------------------------------------
-- Server version	10.1.48-MariaDB

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `accommodation_availability_check`
--

DROP TABLE IF EXISTS `accommodation_availability_check`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_availability_check` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `entity_id` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entity_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `external_identifier` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `provider` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `pax` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `checkin` datetime NOT NULL,
  `checkout` datetime NOT NULL,
  `created_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `accommodation_category_review_translations`
--

DROP TABLE IF EXISTS `accommodation_category_review_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_category_review_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `accommodation_category_review_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `accommodation_category_review_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=6411139 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `accommodation_condition_translations`
--

DROP TABLE IF EXISTS `accommodation_condition_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_condition_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `accommodation_condition_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `accommodation_condition_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=12915431 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `accommodation_guest_value_translations`
--

DROP TABLE IF EXISTS `accommodation_guest_value_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_guest_value_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `accommodation_guest_value_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `accommodation_guest_value_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=8329 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `accommodation_nearby_place_translations`
--

DROP TABLE IF EXISTS `accommodation_nearby_place_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_nearby_place_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `accommodation_nearby_place_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `accommodation_nearby_place_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=12084702 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `accommodation_room_translations`
--

DROP TABLE IF EXISTS `accommodation_room_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_room_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `accommodation_room_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `accommodation_room_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=11882301 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `accommodation_translations`
--

DROP TABLE IF EXISTS `accommodation_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `accommodation_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `accommodation_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `accommodation_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=925659 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `action_control`
--

DROP TABLE IF EXISTS `action_control`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `action_control` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `related_id` int(11) DEFAULT NULL,
  `action` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `entity_name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `address`
--

DROP TABLE IF EXISTS `address`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `address` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `address` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `latitude` double DEFAULT NULL,
  `longitude` double DEFAULT NULL,
  `is_manual` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `address_translations`
--

DROP TABLE IF EXISTS `address_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `address_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `address_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `address_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=354951 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `advert`
--

DROP TABLE IF EXISTS `advert`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `advert` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `type` int(11) NOT NULL,
  `score` int(11) NOT NULL,
  `company` int(11) DEFAULT NULL,
  `destination` int(11) DEFAULT NULL,
  `product_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_class` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `issuing_country` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `hide_in_contracted` tinyint(1) NOT NULL,
  `expiration_date` datetime DEFAULT NULL,
  `product_quality` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `product_type` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `network_integration` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `template_position` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `identify` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `tags` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `no_index` tinyint(1) NOT NULL,
  `device` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_chain` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_54F1F40B4FBF094F` (`company`),
  KEY `IDX_54F1F40B3EC63EAA` (`destination`),
  KEY `IDX_54F1F40B105E6396` (`product_chain`),
  CONSTRAINT `FK_54F1F40B105E6396` FOREIGN KEY (`product_chain`) REFERENCES `product_chain` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_54F1F40B3EC63EAA` FOREIGN KEY (`destination`) REFERENCES `destination` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_54F1F40B4FBF094F` FOREIGN KEY (`company`) REFERENCES `company` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `advert_translations`
--

DROP TABLE IF EXISTS `advert_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `advert_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `advert_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`),
  KEY `advert_translation_idx` (`locale`,`object_class`,`foreign_key`)
) ENGINE=InnoDB AUTO_INCREMENT=62 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `affiliate`
--

DROP TABLE IF EXISTS `affiliate`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `affiliate` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `instance_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `type` int(11) NOT NULL,
  `is_default` tinyint(1) NOT NULL,
  `use_entity_url` tinyint(1) NOT NULL,
  `default_url` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `default_identify` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `logo` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `use_cookies` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_597AA5CF989D9B62` (`slug`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `alert`
--

DROP TABLE IF EXISTS `alert`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `alert` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `booking` int(11) DEFAULT NULL,
  `user` int(11) DEFAULT NULL,
  `active` tinyint(1) NOT NULL,
  `comment` longtext COLLATE utf8_unicode_ci,
  `date` datetime NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `title` longtext COLLATE utf8_unicode_ci,
  `type` int(11) NOT NULL,
  `hash` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_17FD46C1E00CEDDE` (`booking`),
  KEY `IDX_17FD46C18D93D649` (`user`),
  CONSTRAINT `FK_17FD46C18D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_17FD46C1E00CEDDE` FOREIGN KEY (`booking`) REFERENCES `booking` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=17531 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `analytics_account`
--

DROP TABLE IF EXISTS `analytics_account`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `analytics_account` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `type` varchar(250) COLLATE utf8_unicode_ci NOT NULL,
  `code` varchar(250) COLLATE utf8_unicode_ci NOT NULL,
  `tracks` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `product_class` varchar(250) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_id` varchar(250) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `is_system` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `attraction`
--

DROP TABLE IF EXISTS `attraction`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `attraction` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `web_content` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `location` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `working_hours` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_D503E6B8166A9E37` (`web_content`),
  CONSTRAINT `FK_D503E6B8166A9E37` FOREIGN KEY (`web_content`) REFERENCES `web_content` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `audit_configuration`
--

DROP TABLE IF EXISTS `audit_configuration`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `audit_configuration` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `module` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `options` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `from_date` datetime DEFAULT NULL,
  `to_date` datetime DEFAULT NULL,
  `roles` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `users` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `blacklist`
--

DROP TABLE IF EXISTS `blacklist`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `blacklist` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user` int(11) DEFAULT NULL,
  `hide_result` tinyint(1) NOT NULL,
  `hotel` int(11) DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `type` int(11) NOT NULL,
  `content` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_3B1753858D93D649` (`user`),
  KEY `IDX_3B1753853535ED9` (`hotel`),
  CONSTRAINT `FK_3B1753853535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_3B1753858D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=50585 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `blocked_entity`
--

DROP TABLE IF EXISTS `blocked_entity`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `blocked_entity` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `entity_id` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entity_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `blocked_user` int(11) NOT NULL,
  `blocked_time` datetime NOT NULL,
  `blocked_keep_minutes` int(11) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `booking`
--

DROP TABLE IF EXISTS `booking`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `booking` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `reference` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `booking_status` int(11) NOT NULL,
  `client_payment` int(11) NOT NULL,
  `language` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `check_in` datetime NOT NULL,
  `check_out` datetime NOT NULL,
  `adults` int(11) NOT NULL,
  `children` int(11) DEFAULT NULL,
  `general_conditions` longtext COLLATE utf8_unicode_ci,
  `special_request` longtext COLLATE utf8_unicode_ci,
  `pension` int(11) NOT NULL,
  `remuneration` int(11) NOT NULL,
  `fee` double NOT NULL,
  `fee_percent` int(11) NOT NULL,
  `fee_collection_date` datetime DEFAULT NULL,
  `payment_date` datetime DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `client_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `client_lastname` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `amount` double NOT NULL,
  `bookingCondition` int(11) NOT NULL,
  `purchase_amount` double DEFAULT NULL,
  `provider_id` int(11) DEFAULT NULL,
  `user_pending_payment` tinyint(1) DEFAULT NULL,
  `currency` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `reason_for_cancellation` longtext COLLATE utf8_unicode_ci,
  `send_email_costumer` tinyint(1) DEFAULT NULL,
  `send_email_hotel` tinyint(1) DEFAULT NULL,
  `send_promotions_costumer` tinyint(1) DEFAULT NULL,
  `origin` int(11) NOT NULL,
  `crm_reference` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `quantity_items` int(11) DEFAULT NULL,
  `original_reference` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `alias_pension` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `alias_booking_conditions` longtext COLLATE utf8_unicode_ci,
  `engine` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `notes` longtext COLLATE utf8_unicode_ci,
  `free_cancellation_condition_date` datetime DEFAULT NULL,
  `booking_reference_data` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `reference_class` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `reference_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `customer` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `payment_id` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_E00CEDDE4C3A3BB` (`payment_id`),
  UNIQUE KEY `UNIQ_E00CEDDE81398E09` (`customer`),
  UNIQUE KEY `UNIQ_E00CEDDE415FF033` (`booking_reference_data`),
  KEY `IDX_E00CEDDEA53A8AA` (`provider_id`),
  CONSTRAINT `FK_E00CEDDE415FF033` FOREIGN KEY (`booking_reference_data`) REFERENCES `booking_reference_data` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_E00CEDDE4C3A3BB` FOREIGN KEY (`payment_id`) REFERENCES `booking_payment_data` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_E00CEDDE81398E09` FOREIGN KEY (`customer`) REFERENCES `customer` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_E00CEDDEA53A8AA` FOREIGN KEY (`provider_id`) REFERENCES `company` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=2536 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `booking_hotel`
--

DROP TABLE IF EXISTS `booking_hotel`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `booking_hotel` (
  `id` int(11) NOT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `address` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `zip` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `city_hotel` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `cc1` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `ufi` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `class` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `currencycode` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `minrate` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `maxrate` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `preferred` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `nr_rooms` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `longitude` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `latitude` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `public_ranking` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `hotel_url` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `photo_url` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_en` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_fr` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_es` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_de` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_nl` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_it` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_pt` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_ja` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_zh` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_pl` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_ru` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_sv` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_ar` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_el` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `desc_no` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `city_unique` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `city_preferred` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `continent_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `review_score` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `review_nr` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `f39` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `booking_item`
--

DROP TABLE IF EXISTS `booking_item`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `booking_item` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `booking_id` int(11) DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `amount` double NOT NULL,
  `adults` int(11) NOT NULL,
  `children` int(11) DEFAULT NULL,
  `single_amount` double NOT NULL,
  `quantity` int(11) NOT NULL,
  `children_age` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `amenities` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `photo` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_78A07503301C60` (`booking_id`),
  CONSTRAINT `FK_78A07503301C60` FOREIGN KEY (`booking_id`) REFERENCES `booking` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `booking_payment_data`
--

DROP TABLE IF EXISTS `booking_payment_data`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `booking_payment_data` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `booking_payment_type` int(11) NOT NULL,
  `amount` double NOT NULL,
  `operation_number` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `card_number` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `card_owner` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `month_expire_card` int(11) DEFAULT NULL,
  `year_expire_card` int(11) DEFAULT NULL,
  `pending_payment` tinyint(1) DEFAULT NULL,
  `card_cvv` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `positiveBalance` double NOT NULL,
  `negativeBalance` double NOT NULL,
  `encryption_key` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `booking_reference_data`
--

DROP TABLE IF EXISTS `booking_reference_data`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `booking_reference_data` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `company_id` int(11) NOT NULL,
  `web_config_use_ssl` tinyint(1) DEFAULT NULL,
  `location_type` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `sale_booking_phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `sale_booking_email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `company_trade_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `company_fiscal_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `company_booking_phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `company_booking_email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `provider_trade_name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `product_seo_domain` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_domain_sale` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_official_website` longtext COLLATE utf8_unicode_ci,
  `product_id` int(11) NOT NULL,
  `web_template_identify` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `cache_item`
--

DROP TABLE IF EXISTS `cache_item`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `cache_item` (
  `id` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `search_key1` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `search_key2` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `search_key3` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `expiration_date` datetime DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `value` longtext COLLATE utf8_unicode_ci,
  `storage` int(11) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `company`
--

DROP TABLE IF EXISTS `company`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `company` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `logo` int(11) DEFAULT NULL,
  `user` int(11) DEFAULT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `trade_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `fiscal_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `fiscal_number` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `booking_phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `booking_email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `type` int(11) NOT NULL,
  `status` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `address` longtext COLLATE utf8_unicode_ci,
  `whatsapp` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `start_whatsapp` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `end_whatsapp` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `profit_percentage` double NOT NULL,
  `activate_search` tinyint(1) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `booking_payment_type` int(11) NOT NULL,
  `iban` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `domain` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `front` int(11) DEFAULT NULL,
  `seo` int(11) DEFAULT NULL,
  `web_configuration` int(11) DEFAULT NULL,
  `cname` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `meta_tags` longtext COLLATE utf8_unicode_ci,
  `contacts_form` int(11) NOT NULL,
  `trade_info_name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `google_search_domain` varchar(150) COLLATE utf8_unicode_ci DEFAULT NULL,
  `google_search_domain_pattern` varchar(150) COLLATE utf8_unicode_ci DEFAULT NULL,
  `country` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_4FBF094F989D9B62` (`slug`),
  UNIQUE KEY `UNIQ_4FBF094FE48E9A13` (`logo`),
  UNIQUE KEY `UNIQ_4FBF094F8D93D649` (`user`),
  UNIQUE KEY `UNIQ_4FBF094FFEFB62F6` (`front`),
  UNIQUE KEY `UNIQ_4FBF094F6C71EC30` (`seo`),
  UNIQUE KEY `UNIQ_4FBF094FFF607B58` (`web_configuration`),
  CONSTRAINT `FK_4FBF094F6C71EC30` FOREIGN KEY (`seo`) REFERENCES `seo` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_4FBF094F8D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`),
  CONSTRAINT `FK_4FBF094FE48E9A13` FOREIGN KEY (`logo`) REFERENCES `file` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_4FBF094FFEFB62F6` FOREIGN KEY (`front`) REFERENCES `file` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_4FBF094FFF607B58` FOREIGN KEY (`web_configuration`) REFERENCES `web_configuration` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=131 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `company_affiliate`
--

DROP TABLE IF EXISTS `company_affiliate`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `company_affiliate` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `company` int(11) DEFAULT NULL,
  `affiliate` int(11) NOT NULL,
  `id_affiliate` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_6A612F3F4FBF094F` (`company`),
  CONSTRAINT `FK_6A612F3F4FBF094F` FOREIGN KEY (`company`) REFERENCES `company` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `company_integration`
--

DROP TABLE IF EXISTS `company_integration`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `company_integration` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=99 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `company_translations`
--

DROP TABLE IF EXISTS `company_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `company_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `company_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `company_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `configuration`
--

DROP TABLE IF EXISTS `configuration`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `configuration` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `item_set` int(11) NOT NULL,
  `item_key` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `item_value` longtext COLLATE utf8_unicode_ci NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `contact`
--

DROP TABLE IF EXISTS `contact`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `contact` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `owner` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `locale` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `subject` int(11) NOT NULL,
  `checkin` datetime DEFAULT NULL,
  `checkout` datetime DEFAULT NULL,
  `adults` int(11) DEFAULT NULL,
  `children` int(11) DEFAULT NULL,
  `flexible_dates` tinyint(1) DEFAULT NULL,
  `comment` longtext COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `reference` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `reference_id` int(11) NOT NULL,
  `token` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `state` int(11) NOT NULL,
  `reference_name` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `sub_destination_name` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `company` int(11) DEFAULT NULL,
  `from_view` int(11) NOT NULL,
  `children_age` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `quality` int(11) DEFAULT NULL,
  `score` int(11) DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `web_template_identify` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `country` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `rooms` int(11) NOT NULL,
  `original_subject_text` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_4C62E638CF60E67C` (`owner`),
  CONSTRAINT `FK_4C62E638CF60E67C` FOREIGN KEY (`owner`) REFERENCES `user` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `contact_action_configuration`
--

DROP TABLE IF EXISTS `contact_action_configuration`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `contact_action_configuration` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `storage_on_crm` tinyint(1) NOT NULL,
  `to_notify_by_email` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `initial_status` int(11) NOT NULL,
  `use_newsletter` tinyint(1) NOT NULL,
  `send_automatic_response` tinyint(1) NOT NULL,
  `send_email_owner` tinyint(1) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=17 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `contact_subject`
--

DROP TABLE IF EXISTS `contact_subject`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `contact_subject` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `subject` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `identify` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `product_type` longtext COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:simple_array)',
  `condition_action` longtext COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:simple_array)',
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `info_message` longtext COLLATE utf8_unicode_ci,
  `response_message` longtext COLLATE utf8_unicode_ci,
  `tags` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `action_configuration` int(11) DEFAULT NULL,
  `product_identifier` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `show_in_product` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_61E11FFB9E10F7CB` (`action_configuration`),
  CONSTRAINT `FK_61E11FFB9E10F7CB` FOREIGN KEY (`action_configuration`) REFERENCES `contact_action_configuration` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `crm_message`
--

DROP TABLE IF EXISTS `crm_message`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `crm_message` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `contact` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `message` longtext COLLATE utf8_unicode_ci,
  `draft` tinyint(1) NOT NULL,
  `system_response` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `send_time` datetime DEFAULT NULL,
  `operator` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_5AF67CE84C62E638` (`contact`),
  CONSTRAINT `FK_5AF67CE84C62E638` FOREIGN KEY (`contact`) REFERENCES `contact` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `currency`
--

DROP TABLE IF EXISTS `currency`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `currency` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `code` varchar(10) COLLATE utf8_unicode_ci NOT NULL,
  `name` varchar(100) COLLATE utf8_unicode_ci DEFAULT NULL,
  `country_code` varchar(10) COLLATE utf8_unicode_ci DEFAULT NULL,
  `country_name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `currency_country_unique_idx` (`code`,`country_code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `currency_rate`
--

DROP TABLE IF EXISTS `currency_rate`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `currency_rate` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `code` varchar(10) COLLATE utf8_unicode_ci NOT NULL,
  `base_code` varchar(10) COLLATE utf8_unicode_ci NOT NULL,
  `rate` double NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `currency_rate_unique_idx` (`code`,`base_code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `customer`
--

DROP TABLE IF EXISTS `customer`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `customer` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `last_name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `email` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `country` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `dni` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `destination`
--

DROP TABLE IF EXISTS `destination`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `destination` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `parent` int(11) DEFAULT NULL,
  `user` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `type` int(11) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime NOT NULL,
  `updated_at` datetime NOT NULL,
  `widget` int(11) DEFAULT NULL,
  `online_travel_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `front` int(11) DEFAULT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `web_configuration` int(11) DEFAULT NULL,
  `tags` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `currency` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `iso_code` varchar(2) COLLATE utf8_unicode_ci DEFAULT NULL,
  `url` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `ufi_code` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `seo_domain` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `preferred_alias` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `web_content` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `front_photo_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_3EC63EAA989D9B62` (`slug`),
  UNIQUE KEY `UNIQ_3EC63EAAFEFB62F6` (`front`),
  UNIQUE KEY `UNIQ_3EC63EAAFF607B58` (`web_configuration`),
  UNIQUE KEY `UNIQ_3EC63EAA166A9E37` (`web_content`),
  KEY `IDX_3EC63EAA3D8E604F` (`parent`),
  KEY `IDX_3EC63EAA8D93D649` (`user`),
  KEY `IDX_3EC63EAA85F91ED0` (`widget`),
  CONSTRAINT `FK_3EC63EAA166A9E37` FOREIGN KEY (`web_content`) REFERENCES `web_content` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3EC63EAA3D8E604F` FOREIGN KEY (`parent`) REFERENCES `destination` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_3EC63EAA85F91ED0` FOREIGN KEY (`widget`) REFERENCES `html_content` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3EC63EAA8D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3EC63EAAFEFB62F6` FOREIGN KEY (`front`) REFERENCES `file` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3EC63EAAFF607B58` FOREIGN KEY (`web_configuration`) REFERENCES `web_configuration` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=129356 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `destination_photos`
--

DROP TABLE IF EXISTS `destination_photos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `destination_photos` (
  `destination_id` int(11) NOT NULL,
  `photo_id` int(11) NOT NULL,
  PRIMARY KEY (`destination_id`,`photo_id`),
  UNIQUE KEY `UNIQ_5A4F7F4E7E9E4C8C` (`photo_id`),
  KEY `IDX_5A4F7F4E816C6140` (`destination_id`),
  CONSTRAINT `FK_5A4F7F4E7E9E4C8C` FOREIGN KEY (`photo_id`) REFERENCES `file` (`id`),
  CONSTRAINT `FK_5A4F7F4E816C6140` FOREIGN KEY (`destination_id`) REFERENCES `destination` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `destination_translations`
--

DROP TABLE IF EXISTS `destination_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `destination_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `destination_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `destination_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=1827787 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `domain`
--

DROP TABLE IF EXISTS `domain`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `domain` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `domain` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `is_domain_sale` tinyint(1) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_A7A91E0B3535ED9` (`hotel`),
  CONSTRAINT `FK_A7A91E0B3535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=39845 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `entity_affiliate`
--

DROP TABLE IF EXISTS `entity_affiliate`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `entity_affiliate` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `affiliateType` int(11) NOT NULL,
  `affiliateId` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `entityId` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entityClass` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `url` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `affiliationIdentify` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `additional_url_params` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `is_preferred` tinyint(1) NOT NULL,
  `countries` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `countries_only` tinyint(1) NOT NULL,
  `affiliation_params` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `identify` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `tag` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `entity_countries` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  PRIMARY KEY (`id`),
  UNIQUE KEY `entity_affiliate_unique_identify` (`identify`),
  KEY `affiliate_entity_search_idx` (`affiliateType`,`entityId`,`entityClass`,`enabled`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `entity_attribute`
--

DROP TABLE IF EXISTS `entity_attribute`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `entity_attribute` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `entity_id` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entity_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `value` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:object)',
  PRIMARY KEY (`id`),
  UNIQUE KEY `entity_attribute_unique_identify` (`entity_id`,`entity_class`,`name`),
  KEY `entity_attributes_idx` (`entity_id`,`entity_class`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `event`
--

DROP TABLE IF EXISTS `event`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `event` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `tourist_destination` int(11) DEFAULT NULL,
  `user` int(11) DEFAULT NULL,
  `seo` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `language` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `web_page_configuration` int(11) DEFAULT NULL,
  `encryption_key` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `meta_tags` longtext COLLATE utf8_unicode_ci,
  `promotional_minimum_price` double DEFAULT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `long_description` longtext COLLATE utf8_unicode_ci,
  `enabled` tinyint(1) DEFAULT NULL,
  `marked_for_remove` tinyint(1) DEFAULT NULL,
  `stop_sales` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `front_photo_id` int(11) DEFAULT NULL,
  `gallery_type` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `official_website` longtext COLLATE utf8_unicode_ci,
  `address_entity` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `sale` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `product_configuration` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_3BAE0AA7989D9B62` (`slug`),
  UNIQUE KEY `UNIQ_3BAE0AA76C71EC30` (`seo`),
  UNIQUE KEY `UNIQ_3BAE0AA73571C1D7` (`address_entity`),
  UNIQUE KEY `UNIQ_3BAE0AA7E54BC005` (`sale`),
  UNIQUE KEY `UNIQ_3BAE0AA77F0FB925` (`product_configuration`),
  KEY `IDX_3BAE0AA75167253D` (`tourist_destination`),
  KEY `IDX_3BAE0AA78D93D649` (`user`),
  CONSTRAINT `FK_3BAE0AA73571C1D7` FOREIGN KEY (`address_entity`) REFERENCES `address` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3BAE0AA75167253D` FOREIGN KEY (`tourist_destination`) REFERENCES `destination` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3BAE0AA76C71EC30` FOREIGN KEY (`seo`) REFERENCES `seo` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3BAE0AA77F0FB925` FOREIGN KEY (`product_configuration`) REFERENCES `product_configuration` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3BAE0AA78D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3BAE0AA7E54BC005` FOREIGN KEY (`sale`) REFERENCES `sale` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `event_grid`
--

DROP TABLE IF EXISTS `event_grid`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `event_grid` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `event_key` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entity_ref_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `entity_ref_class` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `subject` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `data` longtext COLLATE utf8_unicode_ci,
  `event_type` int(11) NOT NULL,
  `event_at` datetime NOT NULL,
  `tags` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `event_grid_search_idx` (`event_key`,`event_type`,`event_at`),
  KEY `event_grid_entity_full_idx` (`event_key`,`event_type`,`event_at`,`entity_ref_id`,`entity_ref_class`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `event_photos`
--

DROP TABLE IF EXISTS `event_photos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `event_photos` (
  `event_id` int(11) NOT NULL,
  `photo_id` int(11) NOT NULL,
  PRIMARY KEY (`event_id`,`photo_id`),
  UNIQUE KEY `UNIQ_3AEF978B7E9E4C8C` (`photo_id`),
  KEY `IDX_3AEF978B71F7E88B` (`event_id`),
  CONSTRAINT `FK_3AEF978B71F7E88B` FOREIGN KEY (`event_id`) REFERENCES `event` (`id`),
  CONSTRAINT `FK_3AEF978B7E9E4C8C` FOREIGN KEY (`photo_id`) REFERENCES `file` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `event_translations`
--

DROP TABLE IF EXISTS `event_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `event_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `event_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `event_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ext_translations`
--

DROP TABLE IF EXISTS `ext_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `ext_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `lookup_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`),
  KEY `translations_lookup_idx` (`locale`,`object_class`,`foreign_key`)
) ENGINE=InnoDB AUTO_INCREMENT=18221429 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `faq`
--

DROP TABLE IF EXISTS `faq`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `faq` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `web_content` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `question` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `answer` longtext COLLATE utf8_unicode_ci NOT NULL,
  `author` longtext COLLATE utf8_unicode_ci,
  `language` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_E8FF75CC166A9E37` (`web_content`),
  CONSTRAINT `FK_E8FF75CC166A9E37` FOREIGN KEY (`web_content`) REFERENCES `web_content` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `file`
--

DROP TABLE IF EXISTS `file`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `file` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `path` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `type` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `reference` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `reference_id` int(11) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=15997906 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel`
--

DROP TABLE IF EXISTS `hotel`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `tourist_destination` int(11) DEFAULT NULL,
  `user` int(11) DEFAULT NULL,
  `sale` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `seo` int(11) DEFAULT NULL,
  `language` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `tax_imposed` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `places` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `web_page_configuration` int(11) NOT NULL,
  `encryption_key` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `meta_tags` longtext COLLATE utf8_unicode_ci,
  `redirect_visitor_by_country` tinyint(1) NOT NULL,
  `related_option` int(11) NOT NULL,
  `related_title` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `vika_subdomain` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `seo_domain` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `accommodations` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `promotional_minimum_price` double DEFAULT NULL,
  `url` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `long_description` longtext COLLATE utf8_unicode_ci,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `stop_sales` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `quality` int(11) NOT NULL,
  `redirect_country` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `favourite` tinyint(1) NOT NULL,
  `gallery_type` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `use_online_travel_search` tinyint(1) DEFAULT NULL,
  `to_consider` longtext COLLATE utf8_unicode_ci,
  `show_certificate` tinyint(1) NOT NULL,
  `official_website` longtext COLLATE utf8_unicode_ci,
  `service_condition_updated_at` datetime DEFAULT NULL,
  `alias` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `front_photo_id` int(11) DEFAULT NULL,
  `has_added_html_content` tinyint(1) DEFAULT NULL,
  `opportunity_audit` tinyint(1) NOT NULL,
  `map_audit` int(11) NOT NULL,
  `contacts_form` int(11) NOT NULL,
  `extra_info` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `marked_for_remove` tinyint(1) NOT NULL,
  `last_ranking` int(11) DEFAULT NULL,
  `links_updated_at` datetime DEFAULT NULL,
  `domain_sale` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `related_hotels` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `rack` int(11) NOT NULL,
  `score_review` double DEFAULT NULL,
  `score_review_based_on` double DEFAULT NULL,
  `zip` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `room_photo_id` int(11) DEFAULT NULL,
  `content_updated_at` datetime DEFAULT NULL,
  `address_entity` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `update_state` int(11) NOT NULL,
  `last_contact_form_at` datetime DEFAULT NULL,
  `social_links` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `product_configuration` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `web_configuration` int(11) DEFAULT NULL,
  `has_content_available` tinyint(1) NOT NULL DEFAULT '1',
  `has_name_changed` tinyint(1) NOT NULL DEFAULT '0',
  `type` int(11) NOT NULL,
  `universal_code` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `tags` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:simple_array)',
  `product_chain` int(11) DEFAULT NULL,
  `availability_form` int(11) NOT NULL,
  `alternate_domain` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `global_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `total_bookings` int(11) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_3535ED9989D9B62` (`slug`),
  UNIQUE KEY `accommodation_seo_domain_unique_idx` (`seo_domain`),
  UNIQUE KEY `UNIQ_3535ED96C71EC30` (`seo`),
  UNIQUE KEY `UNIQ_3535ED93571C1D7` (`address_entity`),
  UNIQUE KEY `UNIQ_3535ED9E54BC005` (`sale`),
  UNIQUE KEY `UNIQ_3535ED97F0FB925` (`product_configuration`),
  UNIQUE KEY `UNIQ_3535ED9FF607B58` (`web_configuration`),
  UNIQUE KEY `accommodation_sale_domain_unique_idx` (`domain_sale`),
  UNIQUE KEY `accommodation_alternate_domain_unique_idx` (`alternate_domain`),
  KEY `IDX_3535ED95167253D` (`tourist_destination`),
  KEY `IDX_3535ED98D93D649` (`user`),
  KEY `accommodation_url_idx` (`url`),
  KEY `accommodation_request_search_idx` (`seo_domain`,`domain_sale`,`marked_for_remove`,`enabled`),
  KEY `IDX_3535ED9105E6396` (`product_chain`),
  CONSTRAINT `FK_3535ED9105E6396` FOREIGN KEY (`product_chain`) REFERENCES `product_chain` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED93571C1D7` FOREIGN KEY (`address_entity`) REFERENCES `address` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED95167253D` FOREIGN KEY (`tourist_destination`) REFERENCES `destination` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED96C71EC30` FOREIGN KEY (`seo`) REFERENCES `seo` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED97F0FB925` FOREIGN KEY (`product_configuration`) REFERENCES `product_configuration` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED98D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED9E54BC005` FOREIGN KEY (`sale`) REFERENCES `sale` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_3535ED9FF607B58` FOREIGN KEY (`web_configuration`) REFERENCES `web_configuration` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=332042 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_category_review`
--

DROP TABLE IF EXISTS `hotel_category_review`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_category_review` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `category` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `score` double DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_C7E5F9D03535ED9` (`hotel`),
  CONSTRAINT `FK_C7E5F9D03535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1282267 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_condition`
--

DROP TABLE IF EXISTS `hotel_condition`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_condition` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `hotel` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_39FF9813535ED9` (`hotel`),
  CONSTRAINT `FK_39FF9813535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_guest_value`
--

DROP TABLE IF EXISTS `hotel_guest_value`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_guest_value` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `topic` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `topicComments` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_D647850F3535ED9` (`hotel`),
  CONSTRAINT `FK_D647850F3535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=5278 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_nearby_place`
--

DROP TABLE IF EXISTS `hotel_nearby_place`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_nearby_place` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `category` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `detail` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `distance` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_749318C13535ED9` (`hotel`),
  CONSTRAINT `FK_749318C13535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1323855 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_photos`
--

DROP TABLE IF EXISTS `hotel_photos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_photos` (
  `hotel_id` int(11) NOT NULL,
  `photo_id` int(11) NOT NULL,
  PRIMARY KEY (`hotel_id`,`photo_id`),
  UNIQUE KEY `UNIQ_949C32BE7E9E4C8C` (`photo_id`),
  KEY `IDX_949C32BE3243BB18` (`hotel_id`),
  CONSTRAINT `FK_949C32BE3243BB18` FOREIGN KEY (`hotel_id`) REFERENCES `hotel` (`id`),
  CONSTRAINT `FK_949C32BE7E9E4C8C` FOREIGN KEY (`photo_id`) REFERENCES `file` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_room`
--

DROP TABLE IF EXISTS `hotel_room`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_room` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `adults` int(11) DEFAULT NULL,
  `children` int(11) DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `facilities` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:array)',
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `info` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_C55A87133535ED9` (`hotel`),
  CONSTRAINT `FK_C55A87133535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1096094 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_room_photos`
--

DROP TABLE IF EXISTS `hotel_room_photos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_room_photos` (
  `hotel_room_id` int(11) NOT NULL,
  `photo_id` int(11) NOT NULL,
  PRIMARY KEY (`hotel_room_id`,`photo_id`),
  UNIQUE KEY `UNIQ_97F66C377E9E4C8C` (`photo_id`),
  KEY `IDX_97F66C37875D6EBA` (`hotel_room_id`),
  CONSTRAINT `FK_97F66C377E9E4C8C` FOREIGN KEY (`photo_id`) REFERENCES `file` (`id`),
  CONSTRAINT `FK_97F66C37875D6EBA` FOREIGN KEY (`hotel_room_id`) REFERENCES `hotel_room` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `hotel_url`
--

DROP TABLE IF EXISTS `hotel_url`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `hotel_url` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `url` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `affiliate` int(11) DEFAULT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_8CFCF6D03535ED9` (`hotel`),
  CONSTRAINT `FK_8CFCF6D03535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=136815 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `html_content`
--

DROP TABLE IF EXISTS `html_content`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `html_content` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user` int(11) DEFAULT NULL,
  `title` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `string_identifier` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `type` int(11) NOT NULL,
  `seo` int(11) DEFAULT NULL,
  `hotel` int(11) DEFAULT NULL,
  `company` int(11) DEFAULT NULL,
  `destination` int(11) DEFAULT NULL,
  `template_position` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_6A910E256C71EC30` (`seo`),
  KEY `IDX_6A910E258D93D649` (`user`),
  KEY `IDX_6A910E253535ED9` (`hotel`),
  KEY `IDX_6A910E254FBF094F` (`company`),
  KEY `IDX_6A910E253EC63EAA` (`destination`),
  CONSTRAINT `FK_6A910E253535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_6A910E253EC63EAA` FOREIGN KEY (`destination`) REFERENCES `destination` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_6A910E254FBF094F` FOREIGN KEY (`company`) REFERENCES `company` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_6A910E256C71EC30` FOREIGN KEY (`seo`) REFERENCES `seo` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_6A910E258D93D649` FOREIGN KEY (`user`) REFERENCES `user` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB AUTO_INCREMENT=440 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `html_content_translations`
--

DROP TABLE IF EXISTS `html_content_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `html_content_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `html_content_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `html_content_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=1105 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `integration_network`
--

DROP TABLE IF EXISTS `integration_network`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `integration_network` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `parameters` longtext COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:simple_array)',
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_DA83DE5989D9B62` (`slug`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `integration_network_entity`
--

DROP TABLE IF EXISTS `integration_network_entity`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `integration_network_entity` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `integrationId` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entityId` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entityClass` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `parameter` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `value` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `lexik_trans_unit`
--

DROP TABLE IF EXISTS `lexik_trans_unit`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `lexik_trans_unit` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `key_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `domain` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `key_domain_idx` (`key_name`,`domain`)
) ENGINE=InnoDB AUTO_INCREMENT=908 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `lexik_trans_unit_translations`
--

DROP TABLE IF EXISTS `lexik_trans_unit_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `lexik_trans_unit_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `file_id` int(11) DEFAULT NULL,
  `trans_unit_id` int(11) DEFAULT NULL,
  `locale` varchar(10) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `trans_unit_locale_idx` (`trans_unit_id`,`locale`),
  KEY `IDX_B0AA394493CB796C` (`file_id`),
  KEY `IDX_B0AA3944C3C583C9` (`trans_unit_id`),
  CONSTRAINT `FK_B0AA394493CB796C` FOREIGN KEY (`file_id`) REFERENCES `lexik_translation_file` (`id`),
  CONSTRAINT `FK_B0AA3944C3C583C9` FOREIGN KEY (`trans_unit_id`) REFERENCES `lexik_trans_unit` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5309 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `lexik_translation_file`
--

DROP TABLE IF EXISTS `lexik_translation_file`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `lexik_translation_file` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `domain` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `locale` varchar(10) COLLATE utf8_unicode_ci NOT NULL,
  `extention` varchar(10) COLLATE utf8_unicode_ci NOT NULL,
  `path` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `hash` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `hash_idx` (`hash`)
) ENGINE=InnoDB AUTO_INCREMENT=107 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `link_hotels`
--

DROP TABLE IF EXISTS `link_hotels`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `link_hotels` (
  `hotel_id` int(11) NOT NULL,
  `link_id` int(11) NOT NULL,
  PRIMARY KEY (`hotel_id`,`link_id`),
  KEY `IDX_85C6B2AA3243BB18` (`hotel_id`),
  KEY `IDX_85C6B2AAADA40271` (`link_id`),
  CONSTRAINT `FK_85C6B2AA3243BB18` FOREIGN KEY (`hotel_id`) REFERENCES `hotel` (`id`),
  CONSTRAINT `FK_85C6B2AAADA40271` FOREIGN KEY (`link_id`) REFERENCES `hotel` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `log`
--

DROP TABLE IF EXISTS `log`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `log` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `level` int(11) NOT NULL,
  `status` int(11) NOT NULL,
  `message` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `stack_trace` longtext COLLATE utf8_unicode_ci,
  `layer` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `viewed` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `neighbourhood`
--

DROP TABLE IF EXISTS `neighbourhood`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `neighbourhood` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `web_content` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `subtitle` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_96E72AB3989D9B62` (`slug`),
  KEY `IDX_96E72AB3166A9E37` (`web_content`),
  CONSTRAINT `FK_96E72AB3166A9E37` FOREIGN KEY (`web_content`) REFERENCES `web_content` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `neighbourhood_photos`
--

DROP TABLE IF EXISTS `neighbourhood_photos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `neighbourhood_photos` (
  `neighbourhood_id` int(11) NOT NULL,
  `photo_id` int(11) NOT NULL,
  PRIMARY KEY (`neighbourhood_id`,`photo_id`),
  UNIQUE KEY `UNIQ_4430D1807E9E4C8C` (`photo_id`),
  KEY `IDX_4430D180F05C3E1C` (`neighbourhood_id`),
  CONSTRAINT `FK_4430D1807E9E4C8C` FOREIGN KEY (`photo_id`) REFERENCES `file` (`id`),
  CONSTRAINT `FK_4430D180F05C3E1C` FOREIGN KEY (`neighbourhood_id`) REFERENCES `neighbourhood` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `newsletter_envelope`
--

DROP TABLE IF EXISTS `newsletter_envelope`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `newsletter_envelope` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `record` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `parameters` longtext COLLATE utf8_unicode_ci,
  `delay` int(11) NOT NULL,
  `template` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `newsletter` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `locale` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `subject` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `newsletter_record`
--

DROP TABLE IF EXISTS `newsletter_record`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `newsletter_record` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `subscription` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `product_class` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `product_id` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `tourist_destination` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `sub_destination` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `general_destination` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `tags` longtext COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:array)',
  `from_date` datetime DEFAULT NULL,
  `to_date` datetime DEFAULT NULL,
  `component` int(11) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `locale` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_216EC4D8A3C664D3` (`subscription`),
  CONSTRAINT `FK_216EC4D8A3C664D3` FOREIGN KEY (`subscription`) REFERENCES `newsletter_subscription` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `newsletter_subscription`
--

DROP TABLE IF EXISTS `newsletter_subscription`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `newsletter_subscription` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `notification`
--

DROP TABLE IF EXISTS `notification`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `notification` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user_id` int(11) DEFAULT NULL,
  `type` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `title` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `text` longtext COLLATE utf8_unicode_ci,
  `url` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `reading` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_BF5476CAA76ED395` (`user_id`),
  CONSTRAINT `FK_BF5476CAA76ED395` FOREIGN KEY (`user_id`) REFERENCES `user` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `opinion`
--

DROP TABLE IF EXISTS `opinion`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `opinion` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `hotel` int(11) DEFAULT NULL,
  `client` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `language` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `tag` int(11) NOT NULL,
  `score` int(11) NOT NULL,
  `Review` longtext COLLATE utf8_unicode_ci,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `admin_review` tinyint(1) NOT NULL,
  `event` int(11) DEFAULT NULL,
  `positive` longtext COLLATE utf8_unicode_ci,
  `negative` longtext COLLATE utf8_unicode_ci,
  `title` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `booking_id` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `country` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `destination` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_AB02B0273535ED9` (`hotel`),
  KEY `IDX_AB02B0273BAE0AA7` (`event`),
  KEY `IDX_AB02B0273EC63EAA` (`destination`),
  CONSTRAINT `FK_AB02B0273535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_AB02B0273BAE0AA7` FOREIGN KEY (`event`) REFERENCES `event` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_AB02B0273EC63EAA` FOREIGN KEY (`destination`) REFERENCES `destination` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `owner_contact`
--

DROP TABLE IF EXISTS `owner_contact`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `owner_contact` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `email` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `web_site` varchar(500) COLLATE utf8_unicode_ci DEFAULT NULL,
  `subject` int(11) NOT NULL,
  `message` longtext COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `reference_id` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `reference_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `product_chain`
--

DROP TABLE IF EXISTS `product_chain`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `product_chain` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `type` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=272 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `product_chain_translations`
--

DROP TABLE IF EXISTS `product_chain_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `product_chain_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `advert_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`),
  KEY `advert_translation_idx` (`locale`,`object_class`,`foreign_key`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `product_configuration`
--

DROP TABLE IF EXISTS `product_configuration`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `product_configuration` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `declareWebSite` tinyint(1) NOT NULL,
  `official_website` longtext COLLATE utf8_unicode_ci,
  `domain_sale` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `ip` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `product_history`
--

DROP TABLE IF EXISTS `product_history`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `product_history` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `entityId` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `entityClass` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `property` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `value` longtext COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `product_history_search_all_idx` (`entityId`,`entityClass`),
  KEY `product_history_search_idx` (`entityId`,`entityClass`,`property`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `promotion`
--

DROP TABLE IF EXISTS `promotion`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `promotion` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel` int(11) DEFAULT NULL,
  `percentage` double NOT NULL,
  `date_from` datetime NOT NULL,
  `date_to` datetime NOT NULL,
  `keywords` longtext COLLATE utf8_unicode_ci,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_C11D7DD13535ED9` (`hotel`),
  CONSTRAINT `FK_C11D7DD13535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `queue`
--

DROP TABLE IF EXISTS `queue`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `queue` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `max_requeue` int(11) NOT NULL,
  `service` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `service_set` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `per_run` int(11) NOT NULL,
  `last_run` datetime DEFAULT NULL,
  `sleep` int(11) NOT NULL,
  `alias` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `monitoring` tinyint(1) NOT NULL,
  `running` tinyint(1) NOT NULL,
  `max_allowed_process_per_message` int(11) NOT NULL,
  `white_list_error` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_7FFD7F635E237E06` (`name`)
) ENGINE=InnoDB AUTO_INCREMENT=1149 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `queue_error`
--

DROP TABLE IF EXISTS `queue_error`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `queue_error` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `queue` int(11) DEFAULT NULL,
  `message` varchar(500) COLLATE utf8_unicode_ci NOT NULL,
  `stack_trace` longtext COLLATE utf8_unicode_ci,
  `message_id` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_9A6BB107FFD7F63` (`queue`),
  CONSTRAINT `FK_9A6BB107FFD7F63` FOREIGN KEY (`queue`) REFERENCES `queue` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `queue_message`
--

DROP TABLE IF EXISTS `queue_message`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `queue_message` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `queue` int(11) DEFAULT NULL,
  `message` longtext COLLATE utf8_unicode_ci NOT NULL,
  `locked` tinyint(1) NOT NULL,
  `requeue` int(11) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `priority` int(11) NOT NULL,
  `delay` int(11) NOT NULL,
  `show_at` datetime NOT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_543FAB417FFD7F63` (`queue`),
  CONSTRAINT `FK_543FAB417FFD7F63` FOREIGN KEY (`queue`) REFERENCES `queue` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ranking`
--

DROP TABLE IF EXISTS `ranking`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `ranking` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `hotel` int(11) DEFAULT NULL,
  `ranking` int(11) NOT NULL,
  `search_term` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_80B839D03535ED9` (`hotel`),
  CONSTRAINT `FK_80B839D03535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `redirect_domain`
--

DROP TABLE IF EXISTS `redirect_domain`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `redirect_domain` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `redirect_from` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `redirect_to` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `solicited_at` datetime NOT NULL,
  `redirect_status` int(11) NOT NULL,
  PRIMARY KEY (`id`),
  KEY `redirect_domain_from_idx` (`redirect_from`),
  KEY `redirect_from_search_idx` (`redirect_from`,`enabled`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `related_hotels`
--

DROP TABLE IF EXISTS `related_hotels`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `related_hotels` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `hotel_origin` int(11) NOT NULL,
  `hotel_related` int(11) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `report`
--

DROP TABLE IF EXISTS `report`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `report` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `type` int(11) NOT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `code` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `configuration` longtext COLLATE utf8_unicode_ci COMMENT '(DC2Type:object)',
  `run_on_background` tinyint(1) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `report_code_unique_idx` (`code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `report_instance`
--

DROP TABLE IF EXISTS `report_instance`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `report_instance` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `status` int(11) NOT NULL,
  `to_notify_email` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `report_code` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `report_name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `created_by` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `report_id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `status_info` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `file` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `resources`
--

DROP TABLE IF EXISTS `resources`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `resources` (
  `web_configuration_id` int(11) NOT NULL,
  `resource_id` int(11) NOT NULL,
  PRIMARY KEY (`web_configuration_id`,`resource_id`),
  UNIQUE KEY `UNIQ_EF66EBAE89329D25` (`resource_id`),
  KEY `IDX_EF66EBAE85977BA2` (`web_configuration_id`),
  CONSTRAINT `FK_EF66EBAE85977BA2` FOREIGN KEY (`web_configuration_id`) REFERENCES `web_configuration` (`id`),
  CONSTRAINT `FK_EF66EBAE89329D25` FOREIGN KEY (`resource_id`) REFERENCES `file` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `role`
--

DROP TABLE IF EXISTS `role`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `role` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `description` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=15 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `sale`
--

DROP TABLE IF EXISTS `sale`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `sale` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `hotel_contract` int(11) NOT NULL,
  `pvp_commission` double NOT NULL,
  `send_booking_email` tinyint(1) DEFAULT NULL,
  `minimum_stay` int(11) NOT NULL,
  `book_release` int(11) NOT NULL,
  `booking_payment` int(11) NOT NULL,
  `advance_payment` double NOT NULL,
  `booking_on_request` tinyint(1) DEFAULT NULL,
  `booking_email` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `booking_phone` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `currency_code` varchar(10) COLLATE utf8_unicode_ci DEFAULT NULL,
  `use_affiliate_shopping_cart` tinyint(1) NOT NULL,
  `show_affiliate_rates` tinyint(1) NOT NULL,
  `use_multi_affiliate_sale` tinyint(1) NOT NULL,
  `send_email_notification` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `secret`
--

DROP TABLE IF EXISTS `secret`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `secret` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `web_content` char(36) COLLATE utf8_unicode_ci DEFAULT NULL COMMENT '(DC2Type:guid)',
  `avatar` int(11) DEFAULT NULL,
  `title` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `profile` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `author` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `slug` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `UNIQ_5CA2E8E5989D9B62` (`slug`),
  UNIQUE KEY `UNIQ_5CA2E8E51677722F` (`avatar`),
  KEY `IDX_5CA2E8E5166A9E37` (`web_content`),
  CONSTRAINT `FK_5CA2E8E5166A9E37` FOREIGN KEY (`web_content`) REFERENCES `web_content` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_5CA2E8E51677722F` FOREIGN KEY (`avatar`) REFERENCES `file` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `seo`
--

DROP TABLE IF EXISTS `seo`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `seo` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `title` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `search_keywords` longtext COLLATE utf8_unicode_ci,
  `description` longtext COLLATE utf8_unicode_ci,
  `keywords` longtext COLLATE utf8_unicode_ci,
  `visits` int(11) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  `use_redirect_301` tinyint(1) DEFAULT NULL,
  `redirect_domain` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `favourite_site_map` tinyint(1) NOT NULL,
  `is_forced` tinyint(1) DEFAULT NULL,
  `indexed` tinyint(1) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=378545 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `seo_translations`
--

DROP TABLE IF EXISTS `seo_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `seo_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `seo_translation_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `seo_translation_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=9439600 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `service`
--

DROP TABLE IF EXISTS `service`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `service` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `hotel` int(11) DEFAULT NULL,
  `name` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `description` longtext COLLATE utf8_unicode_ci,
  `event` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_E19D9AD23535ED9` (`hotel`),
  KEY `IDX_E19D9AD23BAE0AA7` (`event`),
  CONSTRAINT `FK_E19D9AD23535ED9` FOREIGN KEY (`hotel`) REFERENCES `hotel` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_E19D9AD23BAE0AA7` FOREIGN KEY (`event`) REFERENCES `event` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `service_translations`
--

DROP TABLE IF EXISTS `service_translations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `service_translations` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `locale` varchar(8) COLLATE utf8_unicode_ci NOT NULL,
  `object_class` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `field` varchar(32) COLLATE utf8_unicode_ci NOT NULL,
  `foreign_key` varchar(64) COLLATE utf8_unicode_ci NOT NULL,
  `content` longtext COLLATE utf8_unicode_ci,
  PRIMARY KEY (`id`),
  UNIQUE KEY `service_translations_unique_idx` (`locale`,`object_class`,`field`,`foreign_key`) USING BTREE,
  KEY `service_translations_idx` (`locale`,`object_class`,`foreign_key`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=26453737 DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `shopping_cart`
--

DROP TABLE IF EXISTS `shopping_cart`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `shopping_cart` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hotel_id` int(11) DEFAULT NULL,
  `event_id` int(11) DEFAULT NULL,
  `reference` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `details` longtext COLLATE utf8_unicode_ci,
  `check_in` datetime NOT NULL,
  `check_out` datetime NOT NULL,
  `keywords` longtext COLLATE utf8_unicode_ci,
  `nights` int(11) DEFAULT NULL,
  `currency` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_72AAD4F63243BB18` (`hotel_id`),
  KEY `IDX_72AAD4F671F7E88B` (`event_id`),
  CONSTRAINT `FK_72AAD4F63243BB18` FOREIGN KEY (`hotel_id`) REFERENCES `hotel` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_72AAD4F671F7E88B` FOREIGN KEY (`event_id`) REFERENCES `event` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `sync_point`
--

DROP TABLE IF EXISTS `sync_point`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `sync_point` (
  `id` char(36) COLLATE utf8_unicode_ci NOT NULL COMMENT '(DC2Type:guid)',
  `description` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `type` int(11) NOT NULL,
  `enabled` tinyint(1) NOT NULL,
  `created_at` datetime DEFAULT NULL,
  `updated_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping routines for database 'db_0921'
--
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2025-10-23 16:01:51
