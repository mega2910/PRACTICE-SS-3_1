start

? Вводим год ДР
new birth_year number
set birth_year 2007

? Получаем текущее UNIX-время
new timestamp number
set timestamp TIME

? Секунд в году (365*    24*60*60 - это секунд в дне  * 1000  - тут ещё оказывается time содеражит не секунды, а миллисекунды... ужас...)
new sec_per_year number
set sec_per_year 31536000000

? Считаем полные годы с 1970 раз уж секунды считаются с него (PS, оказывается не секунды, а миллисекунды, больше я не старец с возрастом в 55 тысяч лет с лишним
new years_since number
set years_since 0

loop count_years (timestamp > sec_per_year)
    set timestamp timestamp - sec_per_year
    set years_since years_since + 1
end count_years

? Текущий год = 1970 + предыдущий результат
new current_year number
set current_year 1970 + years_since

? Мой возраст в этом году
new age number
set age current_year - birth_year

? Остаток при делении возраста на 10 (age % 10)
new mod10 number
set mod10 age
loop mod10_loop (mod10 > 9)
    set mod10 mod10 - 10
end mod10_loop

? Проверка на юбилей, если mod10 == 0, обожаю все эти костыли)) хах
new i number
set i 1

if (i > mod10)
    log string "В этом году у вас юбилей! Вам " >> age >> " лет."
else
    log string "В этом году юбилей не будет. Вам " >> age >> " лет."
close

finish
