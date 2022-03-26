# atm-software-in-cpp

// Descriptiom:
// I have written this atm program. It was my term project. Each of its line is written by me. I have given description by the university about the project and all of the actions performed through this program were according to that given instructions. Using this program, user will be able to withdraw , check balance , pay utility bills , do mobile top-ups , make credit card payment , get the mini statment of the account from the given date range , transfer funds to other people. I have made seperated functions for each of the action. Get mini statement and funds transfer are still not working because it was my first semester project. And still now we have not been learnt file handling. Remaining all the program is working well. I Have attached .cpp and .exe files as well as i have given code below as well. If you wanna contact me then my email is huzaifairshad173@gmail.com

#include<iostream
#include <ctime>
#include <cstdlib>
using namespace std;
char menu();
int cw();
int cb();
int pub();
int mtu();
int ccp();
int gms();
int ft();
int main()
{
	srand(time(NULL));	
	cout<<endl<<"\t\t\t\t\tWelcome To ABC Bank"<<endl
	<<"After entering the card....Please enter your PIN\n";
	int pin;
	cin>>pin;
	// Default PIN is 1230
	if(pin == 1230)
	{	
		menu();			
	}
	
	else
	{
		for(int i =1; i<4; i++)
		{
			cout<<"Wrong PIN...Please Enter correct PIN You have "<<4-i<<" attempts left\n";
			cin>>pin;
			if(pin == 1230)
	{	
		menu();			
	}		
			if(i==3)
			{
				cout<<"Your card is blocked...Please contect relevent branch";
			}
		}
	}
	return 0;
}

char menu()
{
	cout<<endl<<"\t\t\t\t\tWelcome to home screen...\n"
			<<"Select an option from the menu\n"
			<<"A) Withdraw Cash\n"<<"B) Check Balance\n"<<"C) Get Mini Statement\n"<<"D) Pay Utility Bill\n"
			<<"E) Mobile Top-up\n"<<"F) Credit Card Payment\n"<<"G) Funds Transfer\n"<<"H) Exit\n";
		char response;
		cin>>response;
		switch (response)
		{
		
			case'A':
			case'a':
				cw();	// cw = cash withdrawal
				break;
				
			case 'B':
			case'b':
				cb();	// cb = check balance
			break;
			
			case 'C':
			case 'c': 
					 gms(); // gms = get mini statement
				
			break;	

			case 'D':
			case 'd':
					pub();	// pub = pay utility bills
			break;	
			
			case 'E':
			case 'e':
				mtu();	// mtu = mobile top up
			break;

			case 'F':
				
			case 'f':
				ccp(); // ccp = credit card payment
			break;			

			
			case 'G':
			case 'g':
				      ft(); // ft = funds transfer
			break;						
			
			case 'H':
			case 'h':
				cout<<"\t\t\t\t\t\tTHANK YOU FOR CHOOSING US";
			break;
			default:
                cout<<"\nInvalid Option";
		}

}


int cw()   //cw = cash withdeaw
{
	int balance = 125000;
	cout<<"\t\t\t\t\tYou have selected \"cash withdrawal\"";
	
	cout<<endl<<endl<<"Balance: "<<balance<<endl;
	cout<<"Withdraw amount: ";	
	int a;
	cin>>a;
	if(a<balance)
	{
		cout<<"You have withdraw "<<a<<" Your remainging balance is "<<balance-a;
		cout<<"\nPlease receive your Cash , Card and Receipt\n\t\t\t\t\t Thank you "<<endl;
		menu();
	}
	else
	{
		cout<<"Invalid amount.....\n"
		<<"Please enter suffficient amnount"<<endl;
		cin>>a;
		if (a<balance)
		{
			cout<<"You have withdraw "<<a<<" Your remainging balance is "<<balance-a;	
			cout<<"\nPlease receive your Cash , Card and Receipt\n\t\t\t\t\t Thank you ";
			menu();
		}
		else
		{
			cout<<"You entered invalid amount again\n";
			menu();
			
		}
	}	
}

int cb()  	//cb = check balance
{
	cout<<"\t\t\t\t\tYou have selected \"Check Balance\"";
	int balance = 125000;
	cout<<"\nYour balance is "<<balance<<endl
		<<"Select from the following\n"
		<<"1) Return to menu\n "
		<<"2) Exit \n12";

		int res;
		cin>>res;
		switch(res)	
		
		{
		case 1 :
//		case'a':
		menu();
		break;
		
		case 2 :
		cout<<"\nThank you";
			menu();
		}		
}

int pub() //pub = pay utitility bill 			
{
		cout<<"\t\t\t\t\tYou have selected \"Pay Utility Bill\"";
		int balance = 125000;
		int n = 999 + rand()%10000;
	cout<<"Select an option\n"
		<<"1) Electricity Bill \n 2) PTCL Bill \n 3) Water Bill \n 4) GAS Bill\n";
	int res1;
	cin>>res1;
	switch (res1)
	{
		case 1 :
				cout<<"Your Electricity Bill amount is "
				<<n<<"\nDo you want to proceed transaction\n Type 1 to pay or any number to exit.\n";
				int res;
				cin>>res;
				if(res== 1 )
				{
					if(n<balance)
					{
					 cout<<"\t\t\t\t\tTRANSACTION SUCCESSFUL...\n"
						<<"You have paid "<<n<<" Your remaining balance is "<<balance - n<<endl;	
					 cout<<"Do you want to pay another bill?\t Type 1 to continue or any number to return home\n";
					 
					 int resp;
					 cin>>resp;
					 if(resp == 1 )
					 {
					 	pub();
					 }
					 else
					 {
					 	menu() ;
					 }
					 
					}
					else
					{
						cout<<"Insufficient balance ";
						
					}
				}
				if(res== 0)
				{
					cout<<"WELCOME BACK\n";
					menu() ;
				}
					
		case  2 :
					cout<<"Your PTCL Bill amount is "
				<<n<<"\nDo you want to proceed transaction\n Type 1 to pay or any number to exit.\n";
				int res2;
				cin>>res2;
				if(res2== 1 )
				{
					if(n<balance)
					{
					 cout<<"\t\t\t\t\tTRANSACTION SUCCESSFUL...\n"
						<<"You have paid "<<n<<" Your remaining balance is "<<balance - n<<endl;	
					 cout<<"Do you want to pay another bill?\t Type 1 to continue or any number to return home\n";
					 
					 int resp2;
					 cin>>resp2;
					 if(resp2 == 1 )
					 {
					 	pub();
					 }
					 else
					 {
					 	menu() ;
					 }
					 
					}
					else
					{
						cout<<"Insufficient balance ";
						
					}
				}
				if(res2== 0)
				{
					cout<<"WELCOME BACK\n";
					menu() ;
				}				 		
								
			case 3 :
				

				cout<<"Your Water Bill amount is "
				<<n<<"\nDo you want to proceed transaction\n Type 1 to pay or any number to exit.\n";
				int res3;
				cin>>res3;
				if(res3== 1 )
				{
					if(n<balance)
					{
					 cout<<"\t\t\t\t\tTRANSACTION SUCCESSFUL...\n"
						<<"You have paid "<<n<<" Your remaining balance is "<<balance - n<<endl;	
					 cout<<"Do you want to pay another bill?\t Type 1 to continue or any number to return home\n";
					 
					 int resp3;
					 cin>>resp3;
					 if(resp3 == 1 )
					 {
					 	pub();
					 }
					 else
					 {
					 	menu() ;
					 }
					 
					}
					else
						{
						cout<<"Insufficient balance ";
						
					}
				}
				if(res3== 0)
				{
					cout<<"WELCOME BACK\n";
					menu() ;
				}
			

			case 4 :
				

				cout<<"Your GAS Bill amount is "
				<<n<<"\nDo you want to proceed transaction\n Type 1 to pay or any number to exit.\n";
				int res4;
				cin>>res4;
				if(res4== 1 )
				{
					if(n<balance)
					{
					 cout<<"\t\t\t\t\tTRANSACTION SUCCESSFUL...\n"
						<<"You have paid "<<n<<" Your remaining balance is "<<balance - n<<endl;	
					 cout<<"Do you want to pay another bill?\t Type 1 to continue or any number to return home\n";
					 
					 int resp4;
					 cin>>resp4;
					 if(resp4 == 1 )
					 {
					 	pub();
					 }
					 else
					 {
					 	menu() ;
					 }
					 
					}
					else
					{
						cout<<"Insufficient balance ";
						
					}
				}
				if(res4== 0)
				{
					cout<<"WELCOME BACK\n";
					menu() ;
				}
	}
}

int mtu() //mtu = mobile top up					
{
	cout<<"\t\t\t\t\tYou have selected \"Mobile Top-up\"";
	int balance = 125000;
	cout<<"Select Operator\n"
		<<"1) Mobilink\n2) Ufone\n3) Telenor\n4) Zong\n";
	int res2 = 0;
	cin>>res2;
	switch (res2)
	{
		case 1:
			{
			
			cout<<"You have selected Mobilink\n"
				<<"Select Option\n"
				<<"1) Pre Paid Payment\n 2) Post Paid Payment\n";
			int a1 = 0;
			cin>>a1;
			if(a1 == 1)
			{
				cout<<"\t\t\t\t\tYOU SELECTED PRE PAID PAYMENT\n"
					<<"Enter amount: ";
				int a2 = 0;
				cin>>a2;
				if(a2<balance)
				{
					cout<<"PAYMENT SUCCESSFUL\n"
						<<"You have purchased mobile load of "<<a2<<"\nYour remaining balance is "<<balance-a2;
				}
				else
				{
					cout<<"TRANSACTION FAILED\n"
					    <<"Please try again\n";
					menu();			
				}
			}
			if (a1 == 2)
			{
				cout<<"\t\t\t\t\tYOU SELECTED POST PAID PAYMENT\n";
				int bill = 499 + rand() % 1500;
				if(bill<balance)
				{
					cout<<"Your bill is "<<bill
						<<"\nType 1 to continue or any other number to return home\n";
					int resp;
					cin>>resp;
					if(resp == 1)
					{
						cout<<"You have paid "<<bill<<" Your remaining balance is "<<balance - bill;
						menu() ;
					}
				
					if(resp != 1)
					{
						cout<<"\t\t\t\t\tTHANK YOU";
						menu() ;	
					}								
			
				}
						if(bill>balance)
			{
				cout<<"INSUFFICIENT BALANCE\n"<<"Please try again\n";
				 menu() ;	
			}	
		}		
	}
			case 2 :
				{
						
					cout<<"You have selected Ufone\n"
						<<"Select Option\n"
					<<"1) Pre Paid Payment\n 2) Post Paid Payment\n";
					int a2 = 0;
					cin>>a2;
					if(a2 == 1)
				{
				cout<<"\t\t\t\t\tYOU SELECTED PRE PAID PAYMENT\n"
					<<"Enter amount: ";
				int a3 = 0;
				cin>>a3;
				if(a3<balance)
				{
					cout<<"PAYMENT SUCCESSFUL\n"
						<<"You have purchased mobile load of "<<a3<<"\nYour remaining balance is "<<balance-a3;
				}
				else
				{
					cout<<"TRANSACTION FAILED\n"
					    <<"Please try again\n";
					menu();			
				}
			}
			if (a2 == 2)
			{
				cout<<"\t\t\t\t\tYOU SELECTED POST PAID PAYMENT\n";
				int bill = 499 + rand() % 1500;
				if(bill<balance)
				{
					cout<<"Your bill is "<<bill
						<<"\nType 1 to continue or any other number to exit\n";
					int resp1;
					cin>>resp1;
					if(resp1 == 1)
					{
						cout<<"You have paid "<<bill<<" Your remaining balance is "<<balance - bill;
						menu() ;
					}
				
					if(resp1 != 1)
					{
						cout<<"\t\t\t\t\tTHANK YOU";
						menu() ;	
					}								
			
				}
					if(bill>balance)
					{
						cout<<"INSUFFICIENT BALANCE\n"<<"Please try again\n";
						 menu() ;	
					}
			}
				}
				
				
				
				case 3:
			{
			
			cout<<"You have selected Telenor\n"
				<<"Select Option\n"
				<<"1) Pre Paid Payment\n 2) Post Paid Payment\n";
			int a1 = 0;
			cin>>a1;
			if(a1 == 1)
			{
				cout<<"\t\t\t\t\tYOU SELECTED PRE PAID PAYMENT\n"
					<<"Enter amount: ";
				int a2 = 0;
				cin>>a2;
				if(a2<balance)
				{
					cout<<"PAYMENT SUCCESSFUL\n"
						<<"You have purchased mobile load of "<<a2<<"\nYour remaining balance is "<<balance-a2;
				}
				else
				{
					cout<<"TRANSACTION FAILED\n"
					    <<"Please try again\n";
					menu();			
				}
			}
			if (a1 == 2)
			{
				cout<<"\t\t\t\t\tYOU SELECTED POST PAID PAYMENT\n";
				int bill = 499 + rand() % 1500;
				if(bill<balance)
				{
					cout<<"Your bill is "<<bill
						<<"\nType 1 to continue or any other number to exit\n";
					int resp;
					cin>>resp;
					if(resp == 1)
					{
						cout<<"You have paid "<<bill<<" Your remaining balance is "<<balance - bill;
						menu() ;
					}
				
					if(resp != 1)
					{
						cout<<"\t\t\t\t\tTHANK YOU";
						menu() ;	
					}								
			
				}
						if(bill>balance)
			{
				cout<<"INSUFFICIENT BALANCE\n"<<"Please try again\n";
				 menu() ;	
			}	
		}		
		}
		
		case 4:
			{
			
			cout<<"You have selected Zong\n"
				<<"Select Option\n"
				<<"1) Pre Paid Payment\n 2) Post Paid Payment\n";
			int a1 = 0;
			cin>>a1;
			if(a1 == 1)
			{
				cout<<"\t\t\t\t\tYOU SELECTED PRE PAID PAYMENT\n"
					<<"Enter amount: ";
				int a2 = 0;
				cin>>a2;
				if(a2<balance)
				{
					cout<<"PAYMENT SUCCESSFUL\n"
						<<"You have purchased mobile load of "<<a2<<"\nYour remaining balance is "<<balance-a2;
				}
				else
				{
					cout<<"TRANSACTION FAILED\n"
					    <<"Please try again\n";
					menu();			
				}
			}
			if (a1 == 2)
			{
				cout<<"\t\t\t\t\tYOU SELECTED POST PAID PAYMENT\n";
				int bill = 499 + rand() % 1500;
				if(bill<balance)
				{
					cout<<"Your bill is "<<bill
						<<"\nType 1 to continue or any other number to exit\n";
					int resp;
					cin>>resp;
					if(resp == 1)
					{
						cout<<"You have paid "<<bill<<" Your remaining balance is "<<balance - bill;
						menu() ;
					}
				
					if(resp != 1)
					{
						cout<<"\t\t\t\t\tTHANK YOU";
						menu() ;	
					}								
			
				}
						if(bill>balance)
			{
				cout<<"INSUFFICIENT BALANCE\n"<<"Please try again\n";
				 menu() ;	
			}	
		}		
	}
	}
}

int ccp() 
{
	cout<<"\t\t\t\t\tYou have selected \"Credit Card Payment\n";
	int balance = 125000;
//	cout<<"You have select Credit Card Payment\n"
	cout<<"Please enter your Credit Card Number\n ";
	int ccNum;
	cin>>ccNum; 
	int a = 999 + rand()%10000;
	cout<<"Your Credit Card Bill is "<<a
		<<"\nDo you want to continue?\tType 1 to continue and any other number to return home.\n";
	int resp;
	cin>>resp;
	
	if(a<balance)
	{
		if (resp == 1)
		{
		
		cout<<"You have Paid "<<a<<" Your remaining balance is "<<balance - a;	
		menu() ;
		}
		else
		{
			cout<<"WELCOME BACK\n";
			menu();
		}
	}		
	else 
	{
		cout<<"INSUFFICIENT BALANCE\n"<<"Please try again\n";
				 menu() ;	
	}
}

int gms()
{
	cout<<"\t\t\t\t\tYou have selected \"Get mini statement\"\n"
		<<"Enter Duration for statement  (mm \ dd \2\ yy) \n"
		<<"From ";
		char date1;
		cin>>date1;
	cout<<"To ";
		char date2;
		cin>>date2;
	int n = 1 + rand()%16000;
	cout<<"You have the following statement\n"<<n<<endl;
		
}

int ft()
{
	int balance = 125000;
	cout<<"\t\t\t\t\tYou have selected \"Funds Transfer\"\n"
		<<"Enter recievers account number\n";
	int ac;
	cin>>ac;
	cout<<"Enter the amount you want to transfer\n";
	int value;
	cin>>value;
	cout<<"You have transfered "<<value<<" to this account "<<ac<<endl
		<<"Your remaining balance is "<<balance - value;
	
	
}

