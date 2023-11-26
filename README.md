# programing_of_coffe_
doing mine function 
 static void display_menu(string[] option, double[] price)
 {
     for (int i = 0; i< option.Length; i++) {
         Console.WriteLine($"{option[i]} --price {price[i]}");
     }
     Console.WriteLine("Please enter the desired Drink from (1-3)");
     int value = Convert.ToInt32(Console.ReadLine());
 }
   static void  place_order(out string suger, out string milk)
 {
     string size;
     string[] Sizes = { "Small", "Medium", "Large" };
     Console.Write("Choose the Size of the drink : \n 1.Small \n 2.Medium \n 3.Large \n  Please choose the Size from (1-3) ");
     int userValue = Convert.ToInt32(Console.ReadLine());
     //size = Sizes[userValue - 1];
     Console.Write("Do You it with Milk :(Yes -NO) :");
     string val = Console.ReadLine();
     milk = (val.ToLower() == "yes") ? "With Milk " : "Without Milk ";
     Console.Write("Do You it with Sugar :(Yes -NO) :");
     val = Console.ReadLine();
     suger = (val.ToLower() == "yes") ? "With Sugar" : "Without Sugar ";


 }
   static double calculate_cost(string[] option, double[] price, string[] size, double[] sizeprice, int op, int sizes, out double totalcost) {
     double priceofCoffe = price[op];
     double priceofSize = sizeprice[sizes];

     totalcost = priceofCoffe + priceofSize;
     return totalcost;
   }
 static void display_order_summary(string[] option, string[] size, string MilkValue,string SugarValue, double totalcost , int op, int sizes) {

     Console.WriteLine($"your Drink is : {option[op]} \n Size : {size[sizes]} , {SugarValue} , {MilkValue} \n Total Price is : {totalcost}");


 }


 static void Main(string[] args)
 {
     string suger, milk;
     int size = 0, option = 0;
     double totalcost;
     string[] opt = { "Lattte", "Cappcino", "amreicano" };
     double[] pri = { 3.65, 2.35, 4 };
     display_menu(opt,pri);
     

     place_order(out suger, out milk);
     string[] Sizes = { "Small", "Medium", "Large" };
     double[] pri2 = { 3.65, 5.77, 7.88 };
     calculate_cost(opt, pri, Sizes ,pri2,option,size,out totalcost );
     //int value;
     //int userValue;
     //string MilkValue;
     //string SugarValue;

     display_order_summary(opt,Sizes,milk,suger,totalcost,option,size);


 }
