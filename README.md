# PhoneBook
/*You are given a phone book that consists of people's names and their phone number. After that you will be given some person's name as query. For each query, print the phone number of that person.

Input Format

The first line will have an integer  denoting the number of entries in the phone book. Each entry consists of two lines: a name and the corresponding phone number.

After these, there will be some queries. Each query will contain a person's name. Read the queries until end-of-file.

Constraints:
A person's name consists of only lower-case English letters and it may be in the format 'first-name last-name' or in the format 'first-name'. Each phone number has exactly 8 digits without any leading zeros.

Output Format

For each case, print "Not found" if the person has no entry in the phone book. Otherwise, print the person's name and phone number. See sample output for the exact format.

To make the problem easier, we provided a portion of the code in the editor. You can either complete that code or write completely on your own.*/
import java.util.*;
import java.io.*;

class Solution{
	public static void main(String []argh)
	{
		/*create a phone book map*/ 
    Map<String,Integer> phoneBook=new HashMap<String,Integer>();
    /*Create input scanner instance*/
        Scanner in = new Scanner(System.in);
        /* Read the number of input phone numbers */
		int n=in.nextInt();
    /* Go to the next line of input */
		in.nextLine();
    /* Loop thru the number of friends, reading the name and phone number, and adding to the phoneBook */
		for(int i=0;i<n;i++)
		{
			String name=in.nextLine();
			int phone=in.nextInt();
			in.nextLine();
      /* Put the name and phone number into the phoneBook */
            phoneBook.put(name, phone);
		}
    /* Loop while there is still more input data */
		while(in.hasNext())
		{
    /* Read the person to search for a phone number */
			String s=in.nextLine();
      /* Does the name exist in the phone Book */
            if(phoneBook.containsKey(s)){
            /* Yes, print out the name and phone number */
                System.out.println(s+"="+phoneBook.get(s));
            }
            else
            /* Print out error message if not found */
            System.out.println("Not found");
		}
	}
}
