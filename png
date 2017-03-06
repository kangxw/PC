#!/user/bin/env Python2.7

import urllib

def getpngurl(url,add):          #检索某个url页面下的png、jpg格式的url保存在add里
    f=urllib.urlopen(url)
    g=open(add,'w')
    for line in f.readlines():
        if 'png' in line or 'jpg' in line and 'http' in line:
            for j in range(len(line)):
                if (line[j]=='p' and line[j+1]=='n' and line[j+2]=='g') or \
                (line[j]=='j' and line[j+1]=='p' and line[j+2]=='g'):
                    end=j+3
                    break
            for i in range(len(line)):
                if line[end-i]=='h' and line[end-i+1]=='t' and line[end-i+2]=='t' and line[end-i+3]=='p':
                    start=end-i
                    break
            g.write(line[start:end])
            g.write('\n')
    g.close()
    print 'Get pngurl DONE!'

def downloadpng(add):   #下载add里的所有png路径的png
    g=open(add,'r')
    t=1
    for line in  g.readlines():
        try:
            b=urllib.urlretrieve(line,'x%d.JPG' %t)
        except IOError,e:
            print 'IOError happened at No.%d' %t,e    
            pass
        t+=1
    g.close()
    print 'Downloadpng DONE'

if __name__=='__main__':
    url='http://www.baidu.com/'
    add='urlpng.txt'
    getpngurl(url,add)
    downloadpng(add)
