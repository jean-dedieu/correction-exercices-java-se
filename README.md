# correction-exercices-java-se

//Programme pour évaluer la valeur d'une voiture


	     /*
	    *Si année de fabrication est  inférieur ou égale à 2000,
	    *la voiture est estimée à 3000 euros
	    *Si l'année de fabrication est supérieur à 2000, sa valeur est estimée à 5000 et plus
	    *Si l'année de fabrication est supérieur à 2000 et que sa marque est renault, sa valuer est estimée à 8000 euros
	    * */
	
	#### Programme
  
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
  
  
  
