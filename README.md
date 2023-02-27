# Movie-Reservation

using System;
using System.Collections.Generic;

namespace booking
{
    internal class Program
    {
        static List<string> referenceNumber = new List<string>() { "123",};
       static List <string> name = new List <string>();
		static List <int> number = new List <int> ();
		static int movieNum;
		static int qntyTix;
		static int timePck;
        static void Main(string[] args)
        {
            Console.WriteLine("=======MOVIE RESERVATION BOOKING TICKETS=======");
            Console.WriteLine("===============================================");
            
            ShowMainMenu();
            
            string userInput = GetUserInput();
            
            while (userInput != "x")
            {
                switch (userInput)
                {
                    case "B":
                    registerBook();
                    ShowMainMenu();
                    userInput = GetUserInput();
                    break;
                    
                case "C":
                   Console.WriteLine("\n=======VIEW YOUR BOOKED TICKETS===========");
                   Console.WriteLine(">> Enter your reference number: ");
                   var reference = Console.ReadLine();
                   
                   if (IsReferenceExists(reference))
                   {
                       Console.WriteLine("\n TSUNA ");
                       Console.WriteLine("\n Movie 1 ");
                       Console.WriteLine("\n Booked Ticket: 2 ");
                       Console.WriteLine("\n 3. 3:20 - 5:00 pm ");
                       userInput = "x";
                   }
                   if (IsReferenceExists(reference))
                   {
                       Console.WriteLine(" " + name );
                       Console.WriteLine(" " + number );
                       Console.WriteLine(" " + movieNum  );
                       Console.WriteLine(" " + qntyTix );
                       Console.WriteLine(" " + timePck );
                   }
                    else
                    {
                        Console.WriteLine("\n!!! reference not found please try again.\n\n");
                        
                        ShowMainMenu();
                        
                        userInput = GetUserInput();
                    }
                    break;
                case "A":
                    Console.WriteLine("\n=================CANCEL BOOKED TICKET====================");
                    Console.WriteLine(">> enter reference number: ");
                    var referenceRemove = Console.ReadLine();
                    
                    if (IsReferenceExists(referenceRemove))
                    {
                        referenceNumber.Remove(referenceRemove);
                        Console.WriteLine("\n!!! Successfully cancelled booking!\n\n");
                        
                        ShowMainMenu();
                        
                        userInput = GetUserInput();
                    }
                    else
                    {
                        Console.WriteLine("\n!!! reference number not found please try again!\n\n");
                        
                        ShowMainMenu();
                        
                        userInput = GetUserInput();
                    }
                    break;
                   }
                }
            }
            
            static void ShowMainMenu()
            {
                Console.WriteLine("============MAIN MENU================");
                Console.WriteLine("Enter B to Book Tickets");
                Console.WriteLine("Enter C to view booked tickets");
                Console.WriteLine("Enter A to cancel your booked tickets");
                Console.WriteLine("Enter x to exit");
                Console.WriteLine("=====================================");
            }
            static string GetUserInput()
            {
                Console.Write(">> user input: ");
                string input = Console.ReadLine();
                
                return input;
            }
            
            static bool IsReferenceExists(string referenceNumber)
            {
                int found = referenceNumber.IndexOf(referenceNumber);
                
                if (found == -1)
                {
                    return false;
                }
                else{
                    return true;
                }
            }
            
            static void registerBook()
            {
            Console.WriteLine("\n============BOOKING FORM==============\n");
                Console.WriteLine(">> Enter your name: ");
                string name = Console.ReadLine();
                //var name = Console.ReadLine();
                Console.WriteLine(">> Enter your number: ");
                string number = Console.ReadLine();
              //  var number = Console.ReadLine();
               Console.WriteLine("=========MOVIES===========");
               Console.WriteLine("Movie 1. One Piece Red Film");
               Console.WriteLine("Movie 2. Detective Conan: The Bride of Halloween");
               Console.WriteLine("Movie 3. Jujutsu Kaisen 0");
               Console.WriteLine("Movie 4. SlamDunk ");
               Console.WriteLine(">> Choose your Movie: ");
              string movieNum = Console.ReadLine();
              // var movie = Console.ReadLine();
               Console.WriteLine(">> Quantity of Ticket: ");
              string qntyTix = Console.ReadLine();
             //  var quantity = Console.ReadLine();
               Console.WriteLine("==========TIME===========");
               Console.WriteLine(" 1. 10:20am-12:00nn ");
               Console.WriteLine(" 2. 1:20pm-3:00pm ");
               Console.WriteLine(" 3. 3:20pm-5:00pm ");
               Console.WriteLine(">> Enter your prefered time: ");
              string timePck = Console.ReadLine();
              // var time = Console.ReadLine();
                Console.WriteLine(">> Enter your id(for reference number): ");
                referenceNumber.Add(Console.ReadLine());
                Console.WriteLine("\n!!! Successfully Booked!\n\n");
            }
                }
                }
