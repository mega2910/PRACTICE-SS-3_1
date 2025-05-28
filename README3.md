start

? вводим год, который проверяем
new year number
set year 2025

? делаем костыль типа имитация year % 4 
new mod4 number
set mod4 year
loop m4 (mod4 > 3)
    set mod4 mod4 - 4
end m4

? ещё один костыль, но теперь с проверкой, т.к. тут хотелось бы поставить if (mod4 == 0), но так нельзя :(
new i number
set i 1

if (i > mod4)
    log string "Год високосным"
else
    log string "Год не високосным"
close

finish
