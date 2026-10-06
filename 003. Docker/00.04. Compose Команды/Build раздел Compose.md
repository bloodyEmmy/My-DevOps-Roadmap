#flashcards/Docker
***
Используется, если нам необходимо самостоятельно собрать [[Образ контейнера (Docker Image)|образ]] из написанного ранее [[Dockerfile]].
***Пример.***
```yaml
services:
	app:
		build:
			context: .
			dockerfile: Dockerfile
```
<!--SR:!2026-08-10,9,250-->
