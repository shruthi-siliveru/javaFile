import java.util.Scanner;
import java.lang.*;
class diffie
{
	public static void main(String args[])
	{
		int msg,p,q,d,e,i,c,m,n,x;

		Scanner s=new Scanner(System.in);
		printf("\nEnter msg: ");
		msg=s.nextInt();
		printf("\nEnter prime num p and q: ");
		p=s.nextInt();
		q=s.nextInt();
		n=p*q;
		x=(p-1)*(q-1);
		e=0;
		for(e=2;e<x;e++)
		{
			if(getGcd(e,x)==1)
				break;
		}
		System.out.println("e: "+e);
		d=0;
		for(i=0;i<=n;i++)
		{
			if((i*e)%x==1)
			{
				d=i;
				break;
			}	
		}
		System.out.println("d: "+d);
		System.out.println("\nPrivate key : "+e+","+n);
		System.out.println("\nPublic key : "+d+","+n);
		c=(int)(Math.pow(msg,e)%n);
		System.out.println("\nciphertext : "+c);
		d=(int)(Math.pow(msg,d)%n);
		printf("\ndecrypted text: "+d);
	}
		
	public static int getGcs(int e,int x)
	{
		if(e==0)
			return x;
		else
			return getGcd(x%e,e)
}			
