# assignment8.1
package com.session8;

public class BankAtm {
	int atmId;
	String bankName;
	String location;
	double balance;
	
	public BankAtm(int atmId, String bankName, String location, double balance) {
		super();
		this.atmId = atmId;
		this.bankName = bankName;
		this.location = location;
		this.balance = balance;
	}
	public void withdraw(double withdrawAmt){
		
		if (balance > 10000 && withdrawAmt < balance){
		       balance = balance - withdrawAmt;
		}
		else {
			throw new BankATMException();
		}
		System.out.println("balance amount after withdrawl is:  " +balance);
	}
		public void deposit(double depositAmt){
			
	    depositAmt = balance + depositAmt;
	    System.out.println("balance amount after deposit is:  " +balance);
	  }

}	


package com.session8;

public class BankATMException extends RuntimeException {
	
	public String getmessage(){
		return " you donot have insufficient fund in the account";
	}

}
package com.session8;

import java.util.Scanner;

public class BankMain {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
       double withdrawAmt, depositAmt;
		Scanner sc = new Scanner(System.in);	
//		int atmId, String bankName, String location, double balance
		
		System.out.println(" Enter Customer atmId:");
		int atmId = sc.nextInt();		
	//	int accNum = sc.nextInt();
		System.out.println(" Enter bank Name:");
		String bankName = sc.next();
		System.out.println(" Enter location:");
        String location = sc.next();
		System.out.println("Customer Current balance:");
		double balance = sc.nextDouble();
		
						
		BankAtm ba = new BankAtm(atmId,bankName, location, balance);	
		System.out.println(" enter withdraw amount:");
		withdrawAmt = sc.nextDouble();
		System.out.println(" enter Deposit amount:");
		depositAmt = sc.nextDouble();		
	    ba.withdraw(withdrawAmt);
	    ba.deposit(depositAmt);
	    
	    BankAtm b = new BankAtm(atmId,bankName, location, balance);		
	    System.out.println(" enter withdraw amount:");
		withdrawAmt = sc.nextDouble();
	    b.withdraw(withdrawAmt);
	    System.out.println(" enter Deposit amount:");
		depositAmt = sc.nextDouble();
		b.deposit(depositAmt);
	    
	    BankAtm c = new BankAtm(atmId,bankName, location, balance);		
	    System.out.println(" enter withdraw amount:");
		withdrawAmt = sc.nextDouble();
		System.out.println(" enter Deposit amount:");
		depositAmt = sc.nextDouble();
			    c.withdraw(withdrawAmt);
	    c.deposit(depositAmt);
	}

}
