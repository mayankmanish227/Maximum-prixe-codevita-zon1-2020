# Maximum-prixe-codevita-zon1-2020

import java.util.*;
import java.io.*;

public class HelloWorld
{
     public static void main(String []args)
     {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        LinkedList<Integer> li=new LinkedList<>();
        for(int i=0;i<n;i++)
        {
            li.add(sc.nextInt());
        }
        System.out.println(mega(li));
     }
     static int mega(LinkedList<Integer> li)
     {
        
         int c=0;
         int p=li.size();

         for(int i=0;i<p-1;i++)
         {
             int b=Collections.max(li);
             int a=li.indexOf(b);
             
             if(a==1)
             {
                 c=c+li.get(a)*li.get(a-1);
                 li.remove(li.get(a-1));
             }
             else if(a>=2)
             {
                 c=c+li.get(a)*li.get(a-1)+li.get(a-2);
                 li.remove(li.get(a-1));    
             }
             
             else if(a<li.size()-2)
             {
                 c=c+li.get(a)*li.get(a+1)+li.get(a+2);
                 li.remove(li.get(a+1));
             }
             else if(a==0)
             {
                 c=c+li.get(a)*li.get(a+1);
                 li.remove(li.get(a+1));
             }
         }
         c=c+li.get(0);
         return c;
     }
}
