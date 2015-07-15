#!/usr/bin/env python

import mechanize
import re
from bs4 import BeautifulSoup

br = mechanize.Browser()
br.set_handle_robots(False)
br.set_handle_refresh(False)
br.addheaders = [('User-agent', 'Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.9.0.1) Gecko/2008071615 Fedora/3.0.1-1.fc9 Firefox/3.0.1')]
br.open('http://www.brightermonday.co.ke')
br.select_form(nr=0)
br.form['username'] = 'username'
br.form['password'] = 'password'
br.submit()


req = br.click_link(text='IT & Telecoms')
br.open(req)
bs = BeautifulSoup(br.response().read(),"lxml")
vacancy = bs.find_all('a', {'title':re.compile('^More')})
for job in vacancy:
	if 'See more' not in job.text:
		print job.text
		
