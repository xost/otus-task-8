# otus-task-7


реализован шаблон "сага"

приложения деплоятся в пространство saga

```
git clone https://github.com/xost/otus-task-8.git

cd otus-task-8

cd auth
skaffold run
cd ../events
skaffold run
cd ../account
skaffold run
cd ../book
skaffold run

```

```mermaid
%% успешная регистрация на мероприятие
    sequenceDiagram
        User ->> Book service: register request
        alt good case
        Book service ->> Event service: occupy slot
        Event service ->> Book service: successfully occupied
        Book service ->> Account service: pay for event
        Account service ->> Book service: successfully paid
        Book service ->> Book service: modify book status to complete
        end
```


