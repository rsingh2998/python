from tkinter import *
import mysql.connector
db=mysql.connector.connect(host="localhost",user="root",password="",database="student")
cur=db.cursor()
import string


def Forget_password():
    def Confirm():
        u=e1.get()
        ph=e2.get()
        old=e3.get()
        new=e4.get()
        con=e5.get()
        print(u,ph,old,new,con)
        sql="SELECT username FROM user WHERE username=%s"
        cur.execute(sql,(u,))
        u1=cur.fetchall()
        cur.execute('SELECT phone_number FROM user where phone_number=%s',(ph,))
        p1=cur.fetchall()
        cur.execute('SELECT password FROM user where password=%s',(old,))
        oldp=cur.fetchall()
        u="[('"+u+"',)]"
        ph="[('"+ph+"',)]"
        old="[('"+old+"',)]"
        
        if(str(u1)!=str(u)):
            from tkinter import messagebox
            messagebox.showerror("Message","Username Does Not match with database")
        elif(str(p1)!=str(ph)):
            from tkinter import messagebox
            messagebox.showerror("Message","Phone Number Does Not match with database")
        elif(str(old)!=str(oldp)):
            from tkinter import messagebox
            messagebox.showerror("Message","Password Does Not match with database")
        elif(new!=con):
            from tkinter import messagebox
            messagebox.showerror("Message","New Password And Confirm Password Does not Match")
        else:
            cur.execute('UPDATE  user SET password=%s WHERE username=%s',(con,u,))
            db.commit()
            from tkinter import messagebox
            messagebox.showinfo("Message","Password Reset Sucessfull")
            r.destroy()
            
            
        
    r=Tk()
    r.geometry("400x300")
    r.title("Reset Form")
    Label(r,text="USERNAME:",fg="blue",bg="cyan",width=20,font=("BOLD",10)).place(x=50,y=50)
    Label(r,text="PHONE NUMBER:",fg="blue",bg="cyan",width=20,font=("BOLD",10)).place(x=50,y=80)
    Label(r,text="OLD PASSWORD:",fg="Blue",bg="cyan",width=20,font=("bold",10)).place(x=50,y=110)
    Label(r,text="NEW PASSWORD:",fg="Blue",bg="cyan",width=20,font=("bold",10)).place(x=50,y=140)
    Label(r,text="COFIRM PASSWORD:",fg="Blue",bg="cyan",width=20,font=("bold",10)).place(x=50,y=170)
    e1=Entry(r,width=20)
    e1.place(x=220,y=52)
    e2=Entry(r,width=20)
    e2.place(x=220,y=82)
    e3=Entry(r,width=20)
    e3.place(x=220,y=112)
    e4=Entry(r,width=20)
    e4.place(x=220,y=142)
    e5=Entry(r,width=20)
    e5.place(x=220,y=172)
    Button(r,text="RESET",command=Confirm,width=20).place(x=150,y=250)
    
    
    


def log():
    u=user.get()
    p=pas.get()
    if(u==""):
        from tkinter import messagebox
        messagebox.showerror("Error","Username Feild Empty")
    elif(p==""):
        from tkinter import messagebox
        messagebox.showerror("Error","Password Feild Empty")

    else:
        sql="SELECT username FROM user WHERE username=%s"
        cur.execute(sql,(u,))
        u1=cur.fetchall()
        cur.execute('SELECT password FROM user where password=%s',(p,))
        p1=cur.fetchall()
        u="[('"+u+"',)]"
        p="[('"+p+"',)]"
        if(str(u1)==str(u) and str(p1)==str(p)):
            from tkinter import messagebox
            messagebox.showinfo("Message","Login Sucessfull")
        else:
            from tkinter import messagebox
            messagebox.showerror("Message","Login failed")
def signup():
    r.bind('<FocusOut>')
    
    
    root=Tk()
    root.title("Registration")

    def ok():
    
        c=variable2.get()
        if(c=='India'):
            OptionMenu(root,variable3,"Andra Pradesh","Arunachal Pradesh","Assam","Bihar","Chhattisgarh","Goa","Gujarat","Haryana","Himachal Pradesh","Jammu and Kashmir","Jharkhand","Karnataka","Kerala","Madya Pradesh","Maharashtra","Manipur","Meghalaya","Mizoram","Nagaland","Orissa","Punjab","Rajasthan","Sikkim","Tamil Nadu","Telagana","Tripura","Uttaranchal","Uttar Pradesh","West Bengal").grid(row=9,column=1)
        elif(c=='Japan'):
            OptionMenu(root,variable3,"Aichi","Saitama","Mie","Ibaraki","Kagawa","Oita","Shiga","Toyama","Okayama","Miyazaki","Tottori","Hiroshima","Kochi","Saga","Kumamoto","Akita","Yamanashi","Fukuoka","Osaka","Shizuoka","Ishikawa","Kyoto","Gunma","Ehime","Hyogo","Okinawa","Fukushima","Gifu","Nagano","Tochigi","Kagoshima","Hokkaid","Kanagawa","Shimane","Miyagi","Nara","Tokyo","Yamagata","Yamaguchi","Fukui","Wakayama","Aomori","Chiba","Iwate","Nagasaki","Tokushima","Niigata").grid(row=9,column=1)
        else:
            print("No city found")

    def pop():
        from tkinter import messagebox
        messagebox.showinfo("Warning!","Please Fill all the Feilds")
    def pop2():
        f_name_text=e1.get()
        l_name_text=e2.get()
        father_name_text=e3.get()
        mother_name_text=e4.get()
        blood_group_text=variable.get()
        address_text=e5.get()
        phone_text=e6.get()
        country_text=variable2.get()
        state_text=variable3.get()
        zip_text=e7.get()
        education_text=variable4.get()
        username=e8.get()
        password=e9.get()
        u2=username
        p2=password
        sql="SELECT username FROM user WHERE username=%s"
        cur.execute(sql,(username,))
        u1=cur.fetchall()
        cur.execute('SELECT password FROM user where password=%s',(password,))
        p1=cur.fetchall()
        username="[('"+username+"',)]"
        if(str(u1)==str(username)):
            from tkinter import messagebox
            messagebox.showerror("Username Error","Username Already Exist")
        
        else: 
            cur.execute('INSERT INTO user VALUES(%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)',(f_name_text,l_name_text,father_name_text,mother_name_text,blood_group_text,address_text,phone_text,country_text,state_text,zip_text,education_text,u2,p2))        
            db.commit()
            from tkinter import messagebox
            messagebox.showinfo("Info","Registration Sucessfull")
            root.destroy()
            r.focus()

            
    def validate():
        f_name_text=e1.get()
        l_name_text=e2.get()
        father_name_text=e3.get()
        mother_name_text=e4.get()
        blood_group_text=variable.get()
        address_text=e5.get()
        phone_text=e6.get()
        country_text=variable2.get()
        state_text=variable3.get()
        zip_text=e7.get()
        education_text=variable4.get()
        username=e8.get()
        password=e9.get()
        if(f_name_text==""):
            pop()
        elif(l_name_text==""):
            pop()
        elif(father_name_text==""):
            pop()
        elif(mother_name_text==""):
            pop()
        elif(blood_group_text=="Select"):
            pop()
        elif(address_text==""):
            pop()
        elif(phone_text==""):
            pop()
        elif(country_text=="Select"):
            pop()
        elif(state_text=="Select"):
            pop()
        elif(zip_text==""):
            pop()
        elif(education_text=="Select"):
            pop()
        elif(username==""):
            pop()
        elif(password==""):
            pop()
        else:
            pop2() 

    
   
    
    
    
    Label(root,text="First Name*",fg="blue",bg="yellow").grid(row=0)

    e1=Entry(root,width=50)
    e1.grid(row=0,column=1)

    Label(root,text="Last Name*",fg="blue",bg="yellow").grid(row=1)
    e2=Entry(root,width=50)
    e2.grid(row=1,column=1)

    Label(root,text="Fathers Name*",fg="blue",bg="yellow").grid(row=2)
    e3=Entry(root,width=50)
    e3.grid(row=2,column=1)


    var=IntVar()
    Label(root,text="Mothers Name*",fg="blue",bg="yellow").grid(row=3)
    e4=Entry(root,width=50)
    e4.grid(row=3,column=1)
    Label(root,text="Gender*",fg="blue",bg="yellow").grid(row=4)

    Radiobutton(root,text="Male",value=1).grid(row=4,column=1)
    Radiobutton(root,text="Female",value=2).grid(row=4,column=2)
    Radiobutton(root,text="Others",value=3).grid(row=4,column=3)

    Label(root,text="Blood Group*",fg="blue",bg="yellow").grid(row=5)
    variable=StringVar()
    variable.set('Select')
    OptionMenu(root,variable,"A+","A-","B+","B-","AB+","AB-","O+","O-").grid(row=5,column=1)

    Label(root,text="Address*",fg="blue",bg="yellow").grid(row=6)
    e5=Entry(root,width=50)
    e5.grid(row=6,column=1)

    Label(root,text="Phone Number*",fg="blue",bg="yellow").grid(row=7)  
    e6=Entry(root,width=50)
    e6.grid(row=7,column=1)

    Label(root,text="Select Country*",fg="blue",bg="yellow").grid(row=8)
    variable2=StringVar()
    variable2.set('Select')
    OptionMenu(root,variable2,"India","Japan","USA","China",).grid(row=8,column=1)
    variable3=StringVar()
    variable3.set('Select') 
    Label(root,text="Select state",fg="blue",bg="yellow").grid(row=9)
    Button(root,text="Ok",command=ok).grid(row=8,column=2)
    Label(root,text="(NOTE: After selecting Country Press ok)").grid(row=8,column=3)


    


    
    Label(root,text="Zip Code*",fg="blue",bg="yellow").grid(row=10)
    e7=Entry(root,width=50)
    e7.grid(row=10,column=1)

    Label(root,text="Education Qualifiction",fg="blue",bg="yellow").grid(row=11)
    variable4=StringVar(root)
    variable4.set('Select')
    OptionMenu(root,variable4,"BCA","BBA","MBA","MCA","B-TECH","M-TECH","BHM","BHMCT","DIPLOMA").grid(row=11,column=1)
    
    Label(root,text="Select Username",fg="blue",bg="yellow").grid(row=12,column=0)
    e8=Entry(root,width=50)
    e8.grid(row=12,column=1)
    
    Label(root,text="Select Password",fg="blue",bg="yellow").grid(row=13,column=0)
    e9=Entry(root,width=50)
    e9.grid(row=13,column=1)
    

    Button(root,text="Submit",command=validate ).grid(row=14,column=5)

    Label(root,text="").grid(row=15)

    mainloop()





    
    
    
    
r=Tk()
r.geometry("400x250")
r.title("Login Form")
Label(r,text="USERNAME:",fg="blue",bg="cyan",width=20,font=("BOLD",10)).place(x=50,y=50)
Label(r,text="PASSWORD:",fg="Blue",bg="cyan",width=20,font=("bold",10)).place(x=50,y=80)
user=StringVar() 
pas=StringVar()
Entry(r,width=20,textvar=user).place(x=220,y=52)
Entry(r,width=20,textvar=pas).place(x=220,y=82)

Button(r,text="Login",width=20,command=log).place(x=150,y=120)
Button(r,text="Signup",width=20,command=signup).place(x=150,y=150)
Button(r,text="Forget Password",width=20,command=Forget_password).place(x=150,y=180)

mainloop()

