start
?вводим переменные
new birth_year number
new birth_month number
new birth_day number

new current_year number
new current_month number
new current_day number

?вводим значения
set birth_year 2007
set birth_month 4
set birth_day 29

set current_year 2025
set current_month 5
set current_day 28

?вводим переменные для расчета  дней (не бейте нас, мудрить сильнее было лень)
new birth_total_days number
new birth_total_days_1 number
new birth_total_days_2 number

?вводим значения через расчеты
new i_1 number
set i_1 0

loop birth_year_ymn (365 > i)
  set birth_total_days_1 birth_total_days_1 +  
end birth_year_ymn


new i_2 number
set i_2 0

loop birth_month_ymn

end birth_month_ymn


set birth_total_days birth_total_days_1 + birth_total_days_2
set birth_total_days birth_total_days + birth_day

log string "вывод проверка " >> birth_total_days_1
log string "вывод проверка " >> birth_total_day
