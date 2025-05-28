start

? вводим переменные
new birth_year number
new birth_month number
new birth_day number

new current_year number
new current_month number
new current_day number

? ввожим значения
set birth_year 2007
set birth_month 4
set birth_day 29

set current_year 2025
set current_month 5
set current_day 28

? переменные для расчета кол-ва дней
new birth_total_days number
new birth_total_days_1 number
new birth_total_days_2 number

new current_total_days number
new current_total_days_1 number
new current_total_days_2 number

? Умножение birth_year * 365 через цикл (жизнь боль)
new i_1 number
set i_1 0
set birth_total_days_1 0

loop birth_year_ymn (birth_year > i_1)
    set birth_total_days_1 birth_total_days_1 + 365
    set i_1 i_1 + 1
end birth_year_ymn

? Умножение birth_month * 30 через цикл
new i_2 number
set i_2 0
set birth_total_days_2 0

loop birth_month_ymn (birth_month > i_2)
    set birth_total_days_2 birth_total_days_2 + 30
    set i_2 i_2 + 1
end birth_month_ymn

? складываем всё в одно (ДР)
set birth_total_days birth_total_days_1 + birth_total_days_2
set birth_total_days birth_total_days + birth_day

? Умножение current_year * 365 через цикл
new i_3 number
set i_3 0
set current_total_days_1 0

loop current_year_ymn (current_year > i_3)
    set current_total_days_1 current_total_days_1 + 365
    set i_3 i_3 + 1
end current_year_ymn

? Умножение current_month * 30 через цикл
new i_4 number
set i_4 0
set current_total_days_2 0

loop current_month_ymn (current_month > i_4)
    set current_total_days_2 current_total_days_2 + 30
    set i_4 i_4 + 1
end current_month_ymn

? складываем всё в одно (СЕЙЧАС)
set current_total_days current_total_days_1 + current_total_days_2
set current_total_days current_total_days + current_day

? Вычисление дни vs дни, только дни - только хардкор, но на самом деле лайт
new age_in_days number
set age_in_days current_total_days - birth_total_days

? Вывод
log string "Возраст в днях: " >> age_in_days

finish
