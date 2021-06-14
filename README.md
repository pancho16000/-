Вариант 7. Приложение для подсчета количества и вывода слов из текстового файла










import re
#this program gets the average number of words per line
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

        #display file contents
        print(contents)
        print('there is an average of', average, 'words per sentence')

        #close the file
        infile.close()
    except IOError:
        print('An error oocurred when trying to read')
        print('the file',filename)

#call main
main()
