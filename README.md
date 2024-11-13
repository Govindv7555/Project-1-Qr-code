# Project-Qr-code
My qr code  website

'''import pickle
def create():
    f=open("binary.dat",'ab')
    opt='y'
    while opt=='y':
        Rollno=int(input('Enter the rollno of the student: '))
        Name=input('Enter the name of the student: ')
        Mark=int(input('Enter the mark of the student: '))
        opt=input('Do you want to continue:(y/n)')
        f1=(Rollno,Name,Mark)
        pickle.dump(f1,f)
    
    f.close()

def display():
    try:
        f = open("binary.dat", 'rb')
        while True:
            try:
                f1 = pickle.load(f)
                print(f1)
            except EOFError:
                break
        f.close()
         
    except FileNotFoundError:
        print('File not found')


def delete(n):
    f=open("binary.dat",'rb')
    r=[]

    try:
        while True:
            f2=pickle.load(f)
            if f2[0]!=n:
                r.append(f2)
                
    except EOFError:
        pass
    
    f.close()
    
    f=open("binary.dat",'wb')
    for i in r:
        pickle.dump(i,f)
        
    f.close()

def modify(m):
    f=open("binary.dat",'rb')
    r=[]
    Modified=False
    try:
        while True:
            f2=pickle.load(f)
            if f2[0]==m:
                b=input('Enter what to modify(Name,Mark)')
                while True:
                    if b=='Name':
                        Name=input('Enter the name of the student: ')
                        Mark=f2[2]
                        f2=(f2[0],Name,Mark)
                        Modified=True
                        break
                    elif b=='Mark':
                        Mark=int(input('Enter the mark of the student: '))
                        Name=f2[1]
                        f2=(f2[0],Name,Mark)
                        Modified=True
                        break
                    else:
                        print('Not in the list')
                        break
               
                
                print('Modified')
            r.append(f2)
    except EOFError:
        pass

    if not Modified:
        print('Not modified')
        return
    f.close()

    f=open("binary.dat",'wb')
    for i in r:
        pickle.dump(i,f)
        
    f.close()


create()
display()
d=input('Do you want to dlt(y/n):')
if d=='y':
    n=int(input('Enter the rollno of the student to be deleted: '))
    delete(n)
else:
    print('Nothing to dlt')
display()
d=input('Do you want to modify(y/n):')
if d=='y':
    m=int(input('Enter the rollno of the student to be modified: '))
    modify(m)
else:
    print('Nothing to modify')
display()'''
