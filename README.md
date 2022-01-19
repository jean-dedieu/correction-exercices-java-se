# correction-exercices-java-se

## Programme inverser les valeurs de 2 variables

          
		System.out.println("Programme inverser les valeurs de 2 variables");
		int a = 10;
		int b = 15;
		int temp;
		temp = a;//ici a = 10, temp = 10;
		a = b; //a = 15, temp = 10, b = 15
		b = temp; //ici a = 15, temp = 10, b = 10
		
		System.out.println(a);
		System.out.println(b);
	
		
## Programme le plus grand de 3 chiffres

             int a, b, c,temp,largest;
	  
		Scanner clavier = new Scanner(System.in);
		
		//have 3 values
		System.out.println("Entrez votre première valeur");
		a = clavier.nextInt();
		System.out.println("Entrez votre deuxième chiffre");
		b = clavier.nextInt();
		System.out.println("Entrez votre 3 ème chiffre");
		c = clavier.nextInt();
		
		//Compare a to be and store the largest of 2 in temporary variable
		temp = a > b ? a:b;
		//Compare the largest between a and b to c and store it as the largest number
		largest = c > temp ? c:temp;
		
		System.out.println("The largest number is " + largest);
		
		
		
		Version ternaire
		
		int a, b, c, largest, temp;  
	    	
	    	//object of the Scanner class 
	    	
	    	Scanner clavier = new Scanner(System.in);  
	    	//reading input from the user  
	    	System.out.println("Entrez le premier chiffre:");  
	    	a = clavier.nextInt();  
	    	System.out.println("Entrez le deuxième chiffre:");  
	    	b = clavier.nextInt();  
	    	System.out.println("Entrez le troisième chiffre:");  
	    	c = clavier.nextInt();  
	    	
	    	//comparing a and b and storing the largest number in a temp variable  
	    	temp = a > b ? a:b; 
	    	
	    	//comparing the temp variable with c and storing the result in the variable  
	    	largest = c > temp ? c:temp;  
	    	
	    	//prints the largest number  
	    	System.out.println("The largest number is: "+largest); 
	    
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
        
	     }else if (manufacturingYear > 2000 && brand.equals("Renault")) {
       
		   System.out.println("Votre voiture est estimée à 5000 et plus");
       
        }else if (manufacturingYear > 2008 ) {
		     System.out.println("Votre voiture est estimée à 8000 euros");
	       }else {
		     System.out.println("Valeur inconnue");
	      }
	        }	
  
  
### Programme distributeur d'argent
  
       final String BANK_NAME = "La poste";
		int accountBalance = 3000;
		int withdrawAmount;
		int depositAmount;

		System.out.println("Bienvenu chez " + BANK_NAME);
		Scanner clavier = new Scanner(System.in);
		System.out.println("Veuillez entrer votre nom");
		String name = clavier.nextLine();
		System.out.println("Bienvenue chez " + BANK_NAME + " " + name);

		// ask the action the custommer would like to do
		System.out.println("Voulez-vous retirer ou déposer ? " + "Pour retirer tapez 1, pour déposer tapez 2");
		
		int questionActionResponse = clavier.nextInt();

		if (questionActionResponse == 1) {
			System.out.println("Combien voulez-vous retirer ?");

		
			withdrawAmount = clavier.nextInt();

			if (withdrawAmount <= accountBalance) {
				accountBalance = accountBalance - withdrawAmount;
				System.out.println("Veuillez prendre votre argent");
				System.out.println(name + " " + ", il vous reste " + accountBalance + " Sur votre compte\nAurevoir");
			}

		} else if (questionActionResponse == 2) {
			System.out.println("Combien voulez-vous déposer");
			
			depositAmount = clavier.nextInt();

			if (depositAmount > 0) {
				accountBalance = accountBalance + depositAmount;
				System.out.println("Votre argent a été bien déposé");
				System.out.println(name + " " + ", Votre nouveau solde est " + accountBalance + "\nAurevoir");
			}

		} else {
			System.out.println("Action inconnue");
			
		}
         
  ## Programme Exercice défi morpio
  
     package morpiobasic;

    import java.util.Arrays;
 
    import java.util.InputMismatchException;
 
    import java.util.Scanner;

      public class App {
      public static void main(String[] args) {

        boolean inMatch = true;
        // Code to get players names
        String player1 = getPlayerName(1);
        String player2 = getPlayerName(2);

        while(inMatch) {
            // Creates a list of 9 positions
            String[] cases = new String[9];
            // At the beggining the 9 positions are empty
            for(int i=0; i< cases.length; i++) {
                cases[i] = " ";
            }
            boolean endGame = true;
            //Loop
            while(endGame) {
                assignSymbol(cases, player1, "X");
                if (getWinner(cases, "X")) {
                    System.out.print(player1);
                    break;
                } else {
                    assignSymbol(cases, player2, "O");
                    endGame = !getWinner(cases, "O");
                    if (endGame == false) {
                        System.out.print(player2);
                    }
                }
            }
            inMatch = replay();
        }
    }

    public static boolean replay() {
        boolean replay = true;
        String lettre = "y";
        System.out.println("\nvoulez-vous rejouer ? [y/n]");
        Scanner myObj = new Scanner(System.in);
        lettre = myObj.nextLine();
        if (lettre.equals("n")) {
            replay = false;
        }
        return replay;
    }
    //Functions that assigns a symbol to the list of 9 positions
    public static void assignSymbol(String[] cases, String player, String symb) {
        //symb = "X";
        int position = -1;
        createMap(cases);
        System.out.println("à ton tour " + player + " :");

        // Number verification
        boolean isNumber = true;
        while (isNumber) {
            try {
                Scanner myObj = new Scanner(System.in);
                position = myObj.nextInt();
                isNumber = false;
                if (position < 1 || position > 9) {
                    isNumber = true;
                    System.out.println("Commande incorrecte, veuillez sélectionner la position où vous voulez jouer " + player + ":");
                }
            } catch (InputMismatchException exception) {
                System.out.println("Commande incorrecte, veuillez sélectionner la position où vous voulez jouer " + player + ":");
            }
        }
        cases[position - 1] = symb;
    }

    public static String getPlayerName(int playerNumber) {
        // This function returns the name from the player's input
        System.out.println("Nom du joueur " + playerNumber + " ?");
        String userName = "Joueur NN";
        Scanner myObj = new Scanner(System.in);
        userName = myObj.nextLine();
        System.out.println("Your username is:" + userName);
        return userName;
    }

    public static boolean getWinner(String[] cases, String symb) {
        boolean winner = false;
        //String symb = "X";
        //System.out.println("Print all cases" + Arrays.toString(cases));
        if (cases[0].equals(symb) && cases[1].equals(symb) && cases[2].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        } else if (cases[3].equals(symb) && cases[4].equals(symb) && cases[5].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        } else if (cases[6].equals(symb) && cases[7].equals(symb) && cases[8].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        }else if (cases[0].equals(symb) && cases[3].equals(symb) && cases[6].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        }else if (cases[1].equals(symb) && cases[4].equals(symb) && cases[7].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        }else if (cases[2].equals(symb) && cases[5].equals(symb) && cases[8].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        }else if (cases[2].equals(symb) && cases[4].equals(symb) && cases[6].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        }else if (cases[0].equals(symb) && cases[4].equals(symb) && cases[8].equals(symb)) {
            System.out.println("le gagnant est :");
            winner = true;
        }
        return winner;
    }

    public static void createMap(String[] cases) {
        System.out.print("Jeu:\t\t\tPosition:\n" +
                " - - -\t\t\t - - -\t\t\n" +
                "|" + cases[0] + "|" + cases[1] + "|" + cases[2] + "|\t\t\t|1|2|3|\n" +
                " - - -\t\t\t - - -\n" +
                "|" + cases[3] + "|" + cases[4] + "|" + cases[5] + "|\t\t\t|4|5|6|\n" +
                " - - -\t\t\t - - -\n" +
                "|" + cases[6] + "|" + cases[7] + "|" + cases[8] + "|\t\t\t|7|8|9|\n" +
                " - - -\t\t\t - - -\n");
    }
    }

  
