# MyDB Task 02 - Level 01 - Youtube

📍 **Description:**  

This project defines a relational database schema for managing a video-sharing platform. The schema includes entities for users, videos, channels, categories, comments, likes, and subscriptions.

---
![Alt Text](Task_02_level_01.png)
---

## Tables and Relationships

### 1. `video`
- Stores video details including title, description, file size, duration, thumbnail, and user ownership.
- Tracks publication dates and interaction counts (views, likes, dislikes).
- Linked to `user` via `user_id`.

### 2. `user`
- Stores user information such as email, surname, password, birthday, gender, and location.
- Associated with uploaded videos.

### 3. `country`
- Stores country details with unique codes.
- Linked to `user` via `country_id`.

### 4. `video_category`
- Defines categories for videos.
- Each category has a unique identifier and a name.

### 5. `video_has_video_category`
- Many-to-many relationship between `video` and `video_category`.

### 6. `chanel`
- Represents user-created channels.
- Contains metadata like name, description, and creation date.
- Linked to `user` via `user_id`.

### 7. `subscription`
- Manages user subscriptions to channels.
- Links `user` with `chanel`.

### 8. `comments`
- Stores user comments on videos.
- Each comment has an author (`user_id`), a target video (`video_id`), and a timestamp.

### 9. `user_like`
- Manages likes on videos and comments.
- Links `user` with `video` or `comment`.
- Tracks like action date.

### 10. `playlist`
- Manages user-created playlists.
- Stores playlist name, creation date, and privacy settings.
- Links `user` and `video`.

## Constraints & Indexing
- Primary and foreign keys enforce data integrity.
- Indexes optimize query performance for foreign key relationships.
- Unique constraints ensure data consistency (e.g., unique country codes, video categories).

## Notes
- The database follows `InnoDB` storage engine for transactional support.
- ENUM data types are used for predefined values (e.g., gender, playlist state, like type).
- Foreign key constraints ensure referential integrity between tables.

