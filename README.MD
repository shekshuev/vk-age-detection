## Описание

Блокнот для обучения модели XGBoost для определения возрастной группы пользователя VK.

Для загрузки данных использовался Apache NiFi, данные сохранялись в Mongo DB с большой избыточностью для дальнейшего улучшения модели.

Итоговая F-мера около 0.84 для двух классов.

Список признаков для обучения модели:

```python
columns = [
    "id",                           # айдишник пользователя
    "class",                        # класс 1-5
    "has_photo",                    # есть ли фото у пользователя
    "followers_count",              # количество подписчиков
    "has_occupation",               # есть ли работа
    "friends_count",                # количество друзей
    "online",                       # сколько раз был онлайн за время наблюдения
    "comments_count",               # количество комментариев пользователя
    "comment_stickers_count",       # среднее количество стикеров в комментариях пользователя
    "comment_text_length",          # средняя длина комментария пользователя
    "mean_friend_online",           # среднее количество, сколько раз друзья были онлайн
    "min_friend_online",            # минимальное
    "max_friend_online",            # максимальное
    "mean_friend_age",              # средний возраст друга
    "min_friend_age",               # минимальный
    "max_friend_age",               # максимальный
    "mean_friend_has_photo",        # среднее количество друзей с фото
    "min_friend_has_photo",         # минимальное
    "max_friend_has_photo",         # максимальное
    "mean_friend_followers_count",  # среднее количество подписчиков у друзей
    "min_friend_followers_count",   # минимальное
    "max_friend_followers_count",   # максимальное
    "mean_comments_count",          # среднее количество комментариев в постах в группах пользователя
    "min_comments_count",           # минимальное
    "max_comments_count",           # максимальное
    "mean_has_attachments",         # среднее количество постов с вложениями в группах пользователя
    "min_has_attachments",          # минимальное
    "max_has_attachments",          # максимальное
    "mean_likes_count",             # среднее количество лайков поста в группах пользователя
    "min_likes_count",              # минимальное
    "max_likes_count",              # максимальное
    "mean_reposts_count",           # среднее количество репостов поста в группах пользователя
    "min_reposts_count",            # минимальное
    "max_reposts_count",            # максимальное
    "mean_views_count",             # среднее количество просмотров поста в группах пользователя
    "min_views_count",              # минимальное
    "max_views_count"]              # максимальное
```

## Установка

Для запуска необходим python 3.6 или выше.

```bash
$ git clone https://github.com/shekshuev/vk-age-detection.git
$ cd vk-age-detection
$ python3 -m venv env
$ source env/bin/activate
$ pip install -r requirements.txt
$ jupyter notebook
```
