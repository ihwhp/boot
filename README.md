# ДЗ №8
## Попадаем в систему без пароля
+ Заходим в загрузчик по нажатию клавиши e до старта системы
+ В строке *linux* убираем все после `ro`, добавляем `rd.break` нажимаем *ctrl+x* ![rd break](https://user-images.githubusercontent.com/105001717/174777538-d7d518c9-9b6e-4e9d-ba47-f6acc1cfe130.png)
+ Система загрузится в аварийном режиме. Корень будет смонтирован в *Read-Only 
+ Перемонтируем корень в режим *Read-Write* `mount -o remount,rw /sysroot`
+ Подменяем корень `chroot /sysroot`
+ Меняем пароль `passwd root`
+ Создаем файл `touch /.autorelabel` для устанавки занов меток безопасности SELinux
+ Перезагружаемся  заходим с новым паролем

## Переименовать VG и добавляем модуль
### *Приложен файл boot.log* с выводом утилиты script

![dracut](https://user-images.githubusercontent.com/105001717/174777618-3fcc7568-83ac-4304-90d7-44722dd6f65d.png)
