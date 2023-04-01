Команды для управления пользователями и группами в Linux:

Создание пользователей и групп:
a. useradd - команда для создания нового пользователя. Например, для создания пользователя "user1", используйте следующую команду:

 - sudo useradd user1
b. groupadd - команда для создания новой группы. Например, для создания группы "group1", используйте следующую команду:

 - sudo groupadd group1
Назначение прав и разрешений на файлы и каталоги:
a. chown - команда для изменения владельца файла или каталога. Например, чтобы изменить владельца файла "file1" на пользователя "user1", используйте следующую команду:

bash
 - sudo chown user1 file1
b. chmod - команда для изменения прав доступа к файлам или каталогам. Например, чтобы разрешить чтение, запись и выполнение для владельца файла "file1", используйте следующую команду:

bash
 - sudo chmod u+rwx file1
Удаление пользователей и групп:
a. userdel - команда для удаления пользователя. Например, для удаления пользователя "user1", используйте следующую команду:

 - sudo userdel user1
b. groupdel - команда для удаления группы. Например, для удаления группы "group1", используйте следующую команду:

 - sudo groupdel group1
Изменение паролей пользователей:
a. passwd - команда для изменения пароля пользователя. Например, для изменения пароля пользователя "user1", используйте следующую команду:

 - sudo passwd user1
Это только несколько примеров команд для управления пользователями и группами в Linux. Существует множество других команд и опций для работы с пользователями и группами, которые могут быть использованы в зависимости от конкретных требований и задач.