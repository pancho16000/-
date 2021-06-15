 Введение
1) Текстовая формулировка задачь
2) код данной задачи
3) скриньшот программы

 2.Вариант 7
Задание Написать приложение для подсчета количества и вывода слов из текстового файла 
(указывается в процессе работы программы).

Алгоритм.
 1) Задается путь к файлу (если не удастся, то задавать в коде)
 2)Подсчитываются слова (слово – то, что содержит только буквы)
 3)Выводится на экран количество и список слов (повторы не печатать).
 
 3.Ход работы
  3.1 Код приложения 
  import re
#this program get the average number of words per line
def main():
    try:
        #get name of file
        filename=input('Enter a filename:')

        #open the file
        infile=open(filename,'r')

        #read file contents
        contents=infile.read()
        line = len(re.findall(r'\n', contents))
        count = len(re.findall(r'\w+', contents))
        average = count // line

        #display fie contents
        print(contents)
        print('there is an average of', average, 'words per sentence')

        #closse the file
        infile.close()
    except IOError:
        print('An error oocurred when trying to read ')
        print('the file',filename )

#call main
main()
 
 
