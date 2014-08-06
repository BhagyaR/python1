import sys
import MySQLdb
#connect 
conn = MySQLdb.connect(host="localhost",user="root",passwd="home",db="address_book")
#create a cursor
cursor = conn.cursor()

#Add Records
def Add():
	var = True
	while var:
		nat = raw_input("Enter National Identification number:")
		cc = raw_input("Enter Credit Card number:")
		cc1 = raw_input("Enter CC number:")
		license = raw_input("Enter license number:")
		dl = raw_input("Enter DL number:")
		name = raw_input("Enter a Name:")
		dob = raw_input("Enter Date Of Birth:")
		dob1 = raw_input("Enter DOB:")
		address = raw_input("Enter the Address:")
		mob = raw_input("Enter telephone number:")
		id = raw_input("Enter Email id:")
		city = raw_input("Enter the City:")
		state= raw_input("Enter the State:")
		postcode = raw_input("Enter the Postcode:")
		country = raw_input("Enter the country:")
		cursor.execute("""
			insert into addresses (cc,cc1,nat,license,dl,name,dob,dob1,address,mob,id,city,state,postcode,country)
			values (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)""",(cc,cc1,nat,license,dl,name,dob,dob1,address,mob,id,city,state,postcode,country))                      		
		print "Add Another Record y/n"
		enter = raw_input("Enter the option:")
		if enter == 'y':
			var = True
		else:
			var = False
#Modify Records	 
def Modify():
	ssn = raw_input("Enter the old ssn number to update:")
	newssn = raw_input("Enter the new ssn number:")	
	cursor.execute("""
		update addresses set ssn = %s
		where ssn = %s""",('535-70-6789',ssn))		
#Delete records
def Delete():
	ssn = "ssn is ssn"
	cursor.execute("""
		delete from addresses 
		where ssn=%s""",ssn)
#View Records
def List():
	print 'List the Records'
	cursor.execute("select * from addresses")
	result = cursor.fetchall()
	for record in result:
		print record[0],"-->",record[1],"-->",record[2],"-->",record[3],"-->",record[4],"-->",record[5],"-->",record[6]

def Exit():
	sys.exit()

def printToConsole():
	while True:
		print '1.Add Record'
		print '2.Modify Record'
		print '3.Delete Record'
		print '4.List Record'
		print '5.Exit'
		option = int(raw_input('Enter the Option :'))
		if option == 1:
			Add()
		elif option == 2:
			Modify()
		elif option == 3:
			Delete()
		elif option == 4:
			List()
		elif option == 5:
			Exit()

printToConsole()
