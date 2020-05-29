# CI/CD в Облаке с помощью GitLab

Исходники проекта для вебинара «CI/CD в Облаке с помощью GitLab»

Вы можете собрать исходники блога HUGO самостоятельно:

1. Воспользуйтесь инструкцией https://gohugo.io/getting-started/quick-start/ для базовой настройки своего блога.
2. Добавьте файл — expires.inc https://github.com/golodnyj/webinar_cicd_hugoblog/blob/master/expires.inc
3. Добавьте файл — .gitlab-ci.yml https://github.com/golodnyj/webinar_cicd_hugoblog/blob/master/.gitlab-ci.yml
4. Добавьте файл — Dockerfile https://github.com/golodnyj/webinar_cicd_hugoblog/blob/master/Dockerfile
5. Добавьте файл — k8s.yaml https://github.com/golodnyj/webinar_cicd_hugoblog/blob/master/k8s.yaml

# CI/CD в Облаке с помощью GitLab

В практической части вебинара мы создаем блог с использованием фреймворка [HUGO](https://gohugo.io/) 
для генерации статического содержания. На GitLab опираемся как на основной элемент CI/CD инфрастуруктуры.  
Мы используем Docker как контейнер и для хранения Docker-образов используем Container Registry, 
всю инфраструктуру разворачиваем в кластере Kubernetes.

## Видео вебинара

## Дополнительные источники
1. Актуальная документация по интеграции GitLab и Kubernetes доступна в документации по адресу:
[Непрерывное развертывание контейнеризованных приложений с помощью GitLab](https://cloud.yandex.ru/docs/solutions/infrastructure-management/gitlab-containers)
2. Для базовой настройки блога с применением HUGO можно воспользоваться инструкцией: 
[Quick Start](https://gohugo.io/getting-started/quick-start/)
3. Статья Florent Chauveau: 
[Dockerized Hugo with GitLab CI/CD](https://blog.callr.tech/static-blog-hugo-docker-gitlab/)
4. Пример репозитория с блогом в финальной версии:
[webinar_cicd_hugoblog](https://github.com/golodnyj/webinar_cicd_hugoblog)

## Последовательность действий
### Создать виртуальную машину blog
### Обновим blog и установим дополнительное ПО:
`sudo apt-get update`    
`sudo apt-get install build-essential curl file git`  
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`  
`brew install gcc`  
`brew install kubectl`  
`curl https://storage.yandexcloud.net/yandexcloud-yc/install.sh | bash`  

### Установим и настроим HUGO
Действуем согласно инструкции [Quick Start](https://gohugo.io/getting-started/quick-start/).   
`brew install hugo`  
`hugo new site blog`  
`cd blog`  
`git init`  
`git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke`  
`echo 'theme = "ananke"' >> config.toml`  
`hugo server`  

### Создать виртуальную машину gitlab
### Создать Container Registry
### Создать кластер kubernetes
### Добавить интеграцию в gitlab с kubernetes
### Инсталировать GitLab Runner
### Настроить CI/CD

