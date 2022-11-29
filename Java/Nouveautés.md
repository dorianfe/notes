##  Java records

Vu dans Spring ex: 
record NewCustomerRequest(
			 String name,
			 String email,
			 Integer age
) {

} 
--> Peut être mis dans son propre fichier

Les records sont utilisées pour simplifier les classes de données; le passage de données [[immutable]] entre des objets. Les records permettent de ne pas avoir à écrire le code (généré automatiquement) habituellement nécessaire au bon fonctionnement de la classe: getters, conctructeurs, equals, hashCode, toString... et private *final* pour chaque champ.

#java14
#record
https://www.baeldung.com/java-record-keyword