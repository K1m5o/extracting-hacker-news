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
        
    return(cnt)

cnt = extract_news('https://news.ycombinator.com/')
content += cnt
content += ('<br>------<br>')
content +=('<br><br>End of message')

print('composing email...')

SERVER = 'smtp.gmail.com'
PORT = 587
FROM = ''
TO = '' 
PASS = ''

msg = MIMEMultipart()

msg['subject'] = 'Top News Stories HN [Aitomated Email]' + ' ' + str(now.day) + str(now.month) + '-' + str(now.year)
msg['from'] = FROM
msg['To'] = TO


