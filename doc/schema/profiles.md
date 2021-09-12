# profiles

## Description

<details>
<summary><strong>Table Definition</strong></summary>

```sql
CREATE TABLE `profiles` (
  `id` bigint NOT NULL AUTO_INCREMENT,
  `uuid` varchar(191) COLLATE utf8mb4_unicode_ci NOT NULL,
  `name` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `userId` bigint NOT NULL,
  `createdAt` datetime(3) NOT NULL DEFAULT CURRENT_TIMESTAMP(3),
  `updatedAt` datetime(3) DEFAULT NULL,
  `deleted` tinyint(1) DEFAULT '0',
  `deletedAt` datetime(3) DEFAULT NULL,
  `ignoreIndexField` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`id`),
  UNIQUE KEY `profiles_uuid_key` (`uuid`),
  UNIQUE KEY `profiles_userId_key` (`userId`),
  CONSTRAINT `profiles_userId_fkey` FOREIGN KEY (`userId`) REFERENCES `users` (`id`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci
```

</details>

## Columns

| Name | Type | Default | Nullable | Extra Definition | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | --------------- | -------- | ------- | ------- |
| id | bigint |  | false | auto_increment |  |  |  |
| uuid | varchar(191) |  | false |  |  |  |  |
| name | varchar(191) |  | true |  |  |  |  |
| userId | bigint |  | false |  |  | [users](users.md) |  |
| createdAt | datetime(3) | CURRENT_TIMESTAMP(3) | false | DEFAULT_GENERATED |  |  |  |
| updatedAt | datetime(3) |  | true |  |  |  |  |
| deleted | tinyint(1) | 0 | true |  |  |  |  |
| deletedAt | datetime(3) |  | true |  |  |  |  |
| ignoreIndexField | tinyint(1) | 0 | true |  |  |  |  |

## Constraints

| Name | Type | Definition |
| ---- | ---- | ---------- |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (id) |
| profiles_userId_fkey | FOREIGN KEY | FOREIGN KEY (userId) REFERENCES users (id) |
| profiles_userId_key | UNIQUE | UNIQUE KEY profiles_userId_key (userId) |
| profiles_uuid_key | UNIQUE | UNIQUE KEY profiles_uuid_key (uuid) |

## Indexes

| Name | Definition |
| ---- | ---------- |
| PRIMARY | PRIMARY KEY (id) USING BTREE |
| profiles_userId_key | UNIQUE KEY profiles_userId_key (userId) USING BTREE |
| profiles_uuid_key | UNIQUE KEY profiles_uuid_key (uuid) USING BTREE |

## Relations

![er](profiles.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)