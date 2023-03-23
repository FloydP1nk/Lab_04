# Лабораторная работа №3 ТиМп
Выполнил Ерохин Павел ИУ8-23

    mkdir Lab_04
    mv formatter_lib formatter_ex_lib solvet_lib. solver_app hwllo_world Lab_04/
    cd Lab_04
    mkdir .github
    cd .github
    mkdir worlflows
    cd workflows
    touch CI.yml
#### создали yml файл

``` yml
name: CMake

on: # список триггеров для запуска процесса
 push:
  branches: [main]
 pull_request:
  branches: [main]

jobs: # список задач
 build_Linux: # наименование задачи

  runs-on: ubuntu-latest # система

  steps: # шаги задачи
  - uses: actions/checkout@v3

  - name: Configure Solver # наименование шага задачи
    run: cmake ${{github.workspace}}/solver_app/ -B ${{github.workspace}}/solver_app/build

  - name: Build Solver # наименование шага задачи
    run: cmake --build ${{github.workspace}}/solver_app/build

  - name: Configure HelloWorld # наименование шага задачи
    run: cmake ${{github.workspace}}/hello_world/ -B ${{github.workspace}}/hello_world/build

  - name: Build HelloWorld # наименование шага задачи
    run: cmake --build ${{github.workspace}}/hello_world/build
```
![Снимок экрана 2023-03-23 в 16 47 30](https://user-images.githubusercontent.com/113801739/227231956-5fa22241-e964-4dfc-aae5-0f73bc69af25.png)

