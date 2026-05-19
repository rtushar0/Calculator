import java.util.*;
public class Main {
	public static void main(String[] args) {
	    Scanner sc = new Scanner (System.in);
	    System.out.println("Do your Calculations, and press '=' for result");
	    String str = sc.nextLine();
	    int l = str.length();
	    StringBuilder s1 = new StringBuilder();
	    int n =0, l1=0;
	    char chop ='\0';
	    // This loop will extract first number and first operator
	    for(int i =0 ;i<l; i++){
	          char ch = str.charAt(i);
	          if(ch=='+' || ch == '-' || ch=='*' || ch =='/' || ch=='%' || ch== '=')
	          {
	                n = Integer.parseInt(s1.toString());
	                l1 += s1.length();
	                s1.setLength(0);
	                chop = ch;
	                break;
	              }
	          else
	          s1 = s1.append(ch);
	          }
	          // If user enter only one number then it will simply print that
	          if (chop == '='){
	             System.out.println(n);
	          }  
	          double res = n;
	          // This loop is for calculations
	          for (int i=(l1+1); i<l; i++)
	          {
	              char ch =str.charAt(i);
	              if(ch=='+' || ch == '-' || ch=='*' || ch =='/' || ch=='%' || ch== '=')
	              {
	                   n = Integer.parseInt(s1.toString());
	                   s1.setLength(0);
	                   if(chop == '+')
	                   res = res +n;
	                   if(chop == '-')
	                   res = res -n;
	                   if(chop == '*')
	                   res = res *n;
	                   if(chop == '/')
	                   res = res /n;
	                   if(chop == '%')
	                   res = res %n;
	                   chop = ch;
	               }    
	              else{ 
	              s1 = s1.append(ch);
	                 }    
	              }
	              System.out.println(res);
	}
}
