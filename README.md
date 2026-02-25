


import requests
from bs4 import BeautifulSoup
import smtplib
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
import datetime 

now = datetime.datetime.now()

content = ''

def extract_news(url):
    print ('Extracting Hacker News Stories ...')
    cnt = ''
    cnt +=('<b>HN Top Stories:</b>\n'+'<br>'+'-'*50+'<br>')
    response = request.get(url)
    content = response.content
    soup = BeautifulSoup(content,'html.parser')
    for i, in enumerate(soup.find_all('td',attrs={'class':'title','valign':''})):
        cnt += ((str(i+1)+ '\n' + '<br>') if tag.txt!='more' else '')

        retrun(cnt)

cnt = extract_news('https://news.ycombinator.com/')
content += cnt
content += ('<br>------<br>')
content +=('<br><br>End of message')

print('composing email...')

SERVER = 'smtp.gmail.com'
PORT = 587
FROM = 'akib.khaliq@gmail.com'
TO = 'akib.khaliq@gmail.com' 
PASS = ''


msg = MIMEMultipart()


