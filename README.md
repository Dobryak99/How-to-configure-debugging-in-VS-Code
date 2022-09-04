# How to configure debugging in VS Code on MacOS
Instruction for beginners  how easily configure debugging in VS Code on MacOS (High Sierra).

 Данная инструкция поможет настроить "Отладку" на MacOS.
 
 1. Скачиваем файл по данной ссылке https://go.microsoft.com/fwlink/?LinkID=817244
 2. Разархивируем файл.
 3. Открываем панель "Отладка" в VS Code.
 4. Нажимаем на шестеренку рядом со значком запуска отладки.
 5. Открываеться файл Launch.json.
 6. Далее необходимо открыть корневую папку .vscode на вашем Mac 
 7. Перенести папку lldb, скаченную ранее из архива, в папку .vscode
 8. Далее открываем эту папку по пути lldb/bin/lldb-mi
 9. Нажимаем правую кнопку мыши и нажимаем Option на клавиатуре(для появления дополнительных функций) и выбираем "Скопировать путь до lldb-mi"
 10. Копируем данный текст в файл 
 {
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
      {
        "name": "C/C++: clang++ build and debug active file",
        "type": "cppdbg",
        "request": "launch",
        "program": "${fileDirname}/${fileBasenameNoExtension}",
        "args": [],
        "stopAtEntry": true,
        "cwd": "${workspaceFolder}",
        "environment": [],
        "externalConsole": false,
        "MIMode": "lldb",
        "miDebuggerPath": "ПУТЬ"(В этой строке необходимо указать путь до файла lldb-mi),
        "preLaunchTask": "C/C++: clang++ build active file"
      }
    ]
  }
  11. В строку "miDebuggerPath": вставляем путь который был скопирован ранее.
  12. Все работает!)
