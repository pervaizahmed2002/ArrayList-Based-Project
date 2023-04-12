import java.sql.SQLOutput;
import java.util.*;
import java.util.Scanner;

class Event{
    private String eName;
    private String eVenue;
    private String eDate;

    Event(){
        eName=eVenue=eDate="";

    }

    Event(String n,String v,String d ){
        eName=n;
        eVenue=v;
        eDate=d;
    }

    void print(){
        System.out.println(eName+" : "+eVenue+" : "+eDate);
    }

}


class EventRecorder{
    ArrayList<Event> events;

    EventRecorder(){
        events= new ArrayList<Event>();
    }


    void addEvent(){
        Scanner input=new Scanner(System.in);
        String name="",venue="",date="";
        System.out.print("Enter Name: ");
        name=input.nextLine();
        System.out.print("Enter Venue: ");
        venue=input.nextLine();
        System.out.print("Enter Date: ");
        date=input.nextLine();
        Event e=new Event(name,venue,date);
        events.add(e);
    }
    void printAllEvents(){
        for(int i=0;i<events.size();i++) {
            Event e=events.get(i);
            e.print();
        }


    }

    void search(){
        Scanner input=new Scanner(System.in);
        System.out.println("Enter a Index to Search Event: ");
        int index=input.nextInt();
        System.out.println("Your Search Result is Given Below");
        Event e=events.get(index);
        e.print();
    }


    void remove(){
        Scanner input=new Scanner(System.in);
        System.out.println("Enter a Index to Remove Event: ");
        int index=input.nextInt();
        System.out.println("Your Remove Result is Given Below");
        events.remove(index);
        Event e=events.get(index);
        e.print();
    }
}
public class Display {
    public static void main(String[] args) {
        EventRecorder e=new EventRecorder();
        Scanner input=new Scanner(System.in);

        do {
            System.out.println("1-Add Event");
            System.out.println("2-Print All Events");
            System.out.println("3-Search Event");
            System.out.println("4-Remove Event");
            System.out.println("5-exit");
            int value = input.nextInt();

            switch (value) {
                case 1:
                    e.addEvent();
                    break;
                case 2:
                    e.printAllEvents();
                    break;
                case 3:
                    e.search();
                    break;
                case 4:
                    e.remove();
                    break;
                case 5:
                    System.exit(0);
                    break;
                default:
                    System.out.println("PLease Enter Correct Option");
            }
        } while(true);

    }
}
