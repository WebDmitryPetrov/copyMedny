<<<<<<< HEAD
pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
            stage('Build') {
                steps {
                    sh 'docker build -t clinics:latest .'
=======
// Объявление pipeline
pipeline { 
    // Используем любой свободный Jenkins агент
    agent any
    environment { // Переменные среды
        CI = 'true' // Не требовать input от пользователя
    }
    stages { // Указываем набор этапов по deployment
            stage('Build') { // Создаем этап с названием Build
                steps { // Создаем шаги внутри этапа
                    sh 'docker build -t clinics:latest .' // Вызов команды bash
>>>>>>> master
                }
            }
            stage('Test') {
                steps {
                    sh 'echo Testing Passed'
                }
            }
            stage('Deploy for Development') {
<<<<<<< HEAD
                when {
                    branch 'dev'
                }
                steps {                    
                    sh 'docker container run --rm --detach --publish 3000:3001 --name clinics-dev clinics:latest'
=======
                when { // Условный оператор
                    branch 'dev'// Исполняется только для ветки dev
                }
                steps {
                    sh 'docker container stop clinics-dev'
                    sh 'docker container run  --detach --publish 3000:3001 --name clinics-dev clinics:latest'
>>>>>>> master
                }
            }
            stage('Deploy for Production') {
                when {
                    branch 'master'
                }
                steps { 
                    sh 'docker container stop clinics'
                    sh 'docker container run --rm --detach --publish 3001:3001 --name clinics clinics:latest'
                }
            }
        }
}