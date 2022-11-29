Retourne les indexes des nombres dont la somme = target
ex: {5, 2, 4} target 6
-> {1, 2}
Cela fonctionne s'il n'y a qu'une solution
```java
public int[] twoSum(int[] nums, int target) {
		for (int i = 0; i < nums.length; i++) {
			for (int j = i + 1; j < nums.length; j++) {
				if (nums[i] + nums[j] == target) {
					return new int[]{i,j};
				}
			}
		}
		return nums;
	}
```

Ce code est lent, car il y a une boucle for dans une boucle for (nested), 
cela oblige à parcourir nums[] potentiellement plusieurs fois
Solution plus rapide avec HashMap et un complément (mathématique)
K -> V
1 -> 0 pour que 5 + unChiffre = target, le complément = 1; 
on enregistre ce complément et l'index du chiffre que l'on regarde (5)
pour la suite on continue la boucle sur nums, on vérifie si le chiffre suivant - target
== complément dans la map
```java
public int[] twoSum(int[] nums, int target) {
	Map< Integer, Integer> complements = new HashMap<>();
	for (int i = 0; i < nums.length; i++) {
		Integer complementIndex = complements.get(nums[i]);
		if(complementIndex != null) {
			return new int[]{i, complementIndex};
		}
		complements.put(target - nums[i], i);
		}
		return nums;
	}
```

https://leetcode.com/problems/two-sum/
#complement 
