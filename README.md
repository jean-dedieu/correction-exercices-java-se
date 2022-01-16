# correction-exercices-java-se

## Programme pour évaluer la valeur d'une voiture


	     /*
	     Écrire un programme qui évalue la valeur d'une voiture
	     
	    *Si année de fabrication est  inférieur ou égale à 2000, alorsla voiture est estimée à 3000 euros
	    *Si l'année de fabrication est supérieur à 2000,alors sa valeur est estimée à 5000 euros et plus
	    *Si l'année de fabrication est supérieur à 2000 et que sa marque est "Renault", sa valuer est estimée à 8000 euros
	    *Sinon, la valeur de la voiture est inconnue
	    * 
	    */
	
	// Programme
  
	     int manufacturingYear = 2009;
	     String brand = "Opel";
	
	     if(manufacturingYear <= 2000) {
       
	    	System.out.println("Votre voiture est estimée à 3000 euros");	
        
	     }else if (manufacturingYear > 2000 & brand == "Renault") {
       
		   System.out.println("Votre voiture est estimée à 5000 et plus");
       
        }else if (manufacturingYear > 2008 ) {
		     System.out.println("Votre voiture est estimée à 8000 euros");
	       }else {
		     System.out.println("Valeur inconnue");
	      }
	        }	
  
  
  //Programme distributeur d'argent
  
         public static void main(String args []) {
	final String BANK_NAME = "La poste";
        int accountBalance = 3000;
       int withdrawAmount;
        int depositAmount;
	
	System.out.println("Bienvenu chez " + BANK_NAME);
	Scanner nameClient = new Scanner(System.in);
	System.out.println("Veuillez entrer votre nom");
	String name = nameClient.nextLine();
	System.out.println("Bienvenue chez " + BANK_NAME +" "+ name);
	
	//ask the action the custommer would like to do
	System.out.println("Voulez-vous retirer ou déposer ? "
			+ "Pour retirer tapez 1, pour déposer tapez 2");
	 Scanner questionAction = new Scanner(System.in);
	 int questionActionResponse  = questionAction.nextInt();
	
	
	 if(questionActionResponse == 1) {
		 System.out.println("Combien voulez-vous retirer ?");
		
		 Scanner askWithdrawAmount = new Scanner(System.in);
		 withdrawAmount = askWithdrawAmount.nextInt();
	    
		 if (withdrawAmount <= accountBalance) {
			 accountBalance = accountBalance - withdrawAmount;
			 System.out.println("Veuillez prendre votre argent");
			 System.out.println(name + " " +", Il vous reste " + accountBalance + " Sur votre compte\nAurevoir");
		 }
		 
	 } else if(questionActionResponse == 2) {
		 System.out.println("Combien voulez-vous déposer");
		 Scanner askDepositAmount = new Scanner(System.in);
		 depositAmount = askDepositAmount.nextInt();
	    
		 if (depositAmount > 0) {
			 accountBalance = accountBalance + depositAmount;
			 System.out.println("Votre argent a été bien déposé");
			 System.out.println(name + " " +", Votre nouveau solde est " + accountBalance + "\nAurevoir");
		 }
		 
	 } else {
		 System.out.println("Action inconnue");
	 }
	 
         }
  
  
