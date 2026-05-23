#flashcards
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
