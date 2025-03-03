#include<iostream>
#include<string>
using namespace std;
class Movie_ticket{

    string movie_name;
    float ticket_price;
    int seat_number;
    string customer_name;
    bool seat_booked[100]={false};
    public:
    void getmoviedetails(string name,float price)
    {
        movie_name=name;
        ticket_price=price;   
    }
    void ticket_booking(string name,int seat)
    {
        if (seat_booked[seat]) {
            cout << "Sorry, this seat is already booked. Please choose another seat." << endl;
            return;
        }
        customer_name=name;
        seat_number=seat;
        seat_booked[seat] = true; 
        cout<<"\n";
        cout<<"Ticket Booked Successfully"<<endl;
        cout<<"Movie Name: "<<movie_name<<endl;
        cout<<"Ticket Price: "<<ticket_price<<endl;
        cout<<"Customer Name: "<<customer_name<<endl;
        cout<<"Seat Number: "<<seat_number<<endl;
        cout<<"show time: 10:00 AM"<<endl;
        cout<<"Enjoy the movie"<<endl;
        cout<<"Thank you for booking the ticket"<<endl;
        cout<<"\n";
    }
    
    void ticket_cancel(string name, int seat)
{
    if (!seat_booked[seat])  // Seat was never booked
    {
        cout << "Sorry, this seat is not booked. Please enter the correct seat number." << endl;
        return;
    }

    if (customer_name != name) // If the name doesn't match the stored name
    {
        cout << "Sorry, this ticket is not booked by you. Please enter the correct name." << endl;
        return;
    }

    // Cancel the ticket
    seat_booked[seat] = false;
    cout << "\nTicket Cancelled Successfully" << endl;
    cout << "Movie Name: " << movie_name << endl;
    cout << "Seat Number: " << seat << endl;
    cout << "Show Time: 10:00 AM" << endl;
    cout<<"\n";
}

    string getmoviename()
    {
        return movie_name;
    }

    int getseatnumber()
    {
        return seat_number;
    }
    ~Movie_ticket() {
        cout << "Movie ticket object for " << movie_name << " is being deleted." << endl;
    }

};
int main()
{
    Movie_ticket movie[6]; 
    int type,choice;
    string customer_name;
    int seat_number;
    string movie_names[] = {"BADNAAM", "HOSHIAR SINGH", "CHHAAVA", "SKY FORCE", "DOG MAN", "CAPTAIN AMERICA: BRAVE NEW WORLD"};
    float ticket_prices[] = {200, 250, 400, 100, 500, 300};

    // Initialize movie objects using a loop
    for (int i = 0; i < 6; i++) {
        movie[i].getmoviedetails(movie_names[i], ticket_prices[i]);
    }
    do{
        cout<<"\n";
   cout<<"......MOVIE TICKET BOOKING SYSTEM......"<<endl;
   cout<<"1.PUNBJABI MOVIES"<<endl;
   cout<<"2.HINDI MOVIES"<<endl;
   cout<<"3.ENGLISH MOVIES"<<endl;
   cout<<"4.CANCEL TICKET"<<endl;
   cout<<"5.Exit"<<endl;
   cout<<"\n";
   cout<<"Enter a number to choose an option: "<<endl;
   cin>>type;
   switch(type)
   {
      case 1:
      cout<<"1.BADNAAM"<<endl;
      cout<<"2.HOSHIAR SINGH"<<endl;
      cout<<"Enter the number for the movie you want to watch"<<endl;
        cin>>choice;
        switch(choice)
        {
            
            case 1:
            cout<<"Movie Name:BADNAAM"<<endl;
            cout<<"Ticket Price:200"<<endl;
            cout<<"Enter your name for ticket booking: "<<endl;
            cin.ignore();
            getline(cin,customer_name);
            cout<<"Enter the seat number you want to book: "<<endl;
            cin>>seat_number;
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() == "BADNAAM") {
                    movie[i].ticket_booking(customer_name, seat_number);
                    break;
                }
                
            }
            break;
            case 2:
            cout<<"Movie Name:HOSHIAR SINGH"<<endl;
            cout<<"Ticket Price:250"<<endl;
            cout<<"Enter your name for ticket booking: "<<endl;
            cin.ignore();
            getline(cin,customer_name);
            cout<<"Enter the seat number you want to book: "<<endl;
            cin>>seat_number; 
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() == "HOSHIAR SINGH") {
                    movie[i].ticket_booking(customer_name, seat_number);
                    break;
                }
            
            }         
            break;
            default:
            cout<<"INVALID NUMBER(CHOICE)....ENTER VALID NUMBER(CHOICE)"<<endl;
        }
      break;
      case 2:
      cout<<"1.CHHAAVA"<<endl;
      cout<<"2.SKY FORCE"<<endl;
      cout<<"Enter the number for the movie you want to watch"<<endl;
        cin>>choice;
        switch(choice)
        {
            case 1:
            cout<<"Movie Name:CHHAAVA"<<endl;
            cout<<"Ticket Price:400"<<endl; 
            cout<<"Enter your name for ticket booking: "<<endl;
            cin.ignore();
            getline(cin,customer_name);
            cout<<"Enter the seat number you want to book: "<<endl;
            cin>>seat_number;  
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() == "CHHAAVA") {
                    movie[i].ticket_booking(customer_name, seat_number);
                    break;
                }
                
            }        
            break;
            case 2:
            cout<<"Movie Name:SKY FORCE"<<endl;
            cout<<"Ticket Price:100"<<endl;
            cout<<"Enter your name for ticket booking: "<<endl;
            cin.ignore();
            getline(cin,customer_name);
            cout<<"Enter the seat number you want to book: "<<endl;
            cin>>seat_number; 
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() == "SKY FORCE") {
                    movie[i].ticket_booking(customer_name, seat_number);
                    break;
                }
                
            }       
            break;
            default:
            cout<<"INVALID NUMBER(CHOICE)....ENTER VALID NUMBER(CHOICE)"<<endl;
        }
      break;
      case 3:
      cout<<"1.DOG MAN"<<endl;
      cout<<"2.CAPTAIN AMERICEA:BRAVE NEW WORLD"<<endl;
      cout<<"Enter the number for the movie you want to watch"<<endl;
        cin>>choice;
        switch(choice)
        {
            case 1:
            cout<<"Movie Name:DOG MAN"<<endl;
            cout<<"Ticket Price:500"<<endl;
            cout<<"Enter your name for ticket booking: "<<endl;
            cin.ignore();
            getline(cin,customer_name);
            
            cout<<"Enter the seat number you want to book: "<<endl;
            cin>>seat_number;
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() =="DOG MAN") {
                    movie[i].ticket_booking(customer_name, seat_number);
                    break;
                }
                
            }
            break;
            case 2:
            cout<<"Movie Name:CAPTAIN AMERICA:BRAVE NEW WORLD"<<endl;
            cout<<"Ticket Price:300"<<endl;  
            cout<<"Enter your name for ticket booking: "<<endl;
            cin.ignore();
            getline(cin,customer_name);
            cout<<"Enter the seat number you want to book: "<<endl;
            cin>>seat_number;  
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() == "CAPTAIN AMERICA:BRAVE NEW WORLD") {
                    movie[i].ticket_booking(customer_name, seat_number);
                    break;
                }
                
            }  
            break; 
        }
        case 4:
        {
            string movie_name;
            cout << "Enter the movie name: ";
            cin.ignore();
            getline(cin, movie_name);
    
            cout << "Enter your name to cancel the ticket: ";
            getline(cin, customer_name);
    
            cout << "Enter the seat number you want to cancel: ";
            cin >> seat_number;
    
            bool found = false; // To check if the movie exists
    
            for (int i = 0; i < 6; i++) {
                if (movie[i].getmoviename() == movie_name) {
                    movie[i].ticket_cancel(customer_name, seat_number);
                    found = true;
                    break;
                }
            }
    
            if (!found) {
                cout << "Movie not found. Please enter a valid movie name." << endl;
                cout<<"\n";
            }
        }
        break;
        case 5:
        cout<<"SUCCESSFULLY EXITED"<<endl;
        cout<<"\n";
        break;
        default:
        cout<<"INVALID NUMBER(CHOICE)....ENTER VALID NUMBER(CHOICE)"<<endl;
        break;
    }
    }while(type!=5);

   
return 0;
}

