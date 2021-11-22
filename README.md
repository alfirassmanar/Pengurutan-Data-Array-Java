# Pengurutan-Data-Array-Java
> sorting with java

### Printscreen Program
![Output1](Output%201.png)
![Output2](Output%202.png)

### Source Code Program
```java
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package pengurutan_data;

import java.util.Scanner;

/**
 *
 * @author alfir
 */
public class Pengurutan_data {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String order[] = new String [5]; // [] depan baris [] belakang kolom
        String order2[] = new String[5];     
              
        int nominal [] = new int [5];
        int nominal2[] = new int[5];
                        
        int chose1, chose2, pilih3;
        int index = 0,
            food = 0,
            drink = 0,
            payment,
            change,
            indexfood = 0, 
            indexdrink = 0,
            indextotal = 0,
            amount1 = 0;
       
        
        //inisialisasi data
        order[0] = "Burger ";  nominal[0] = 25000;
        order[1] = "Roti-O ";  nominal[1] = 12000;
        order[2] = "Pizza ";  nominal[2] = 30000;
        order[3] = "Bakpao";  nominal[3] = 10000;
        order[4] = "Hotdong";  nominal[4] = 19000;
        
        // ------------Start Program------------
        System.out.println("--------This just  practice Shorting with Java(Bubble)--------");
        do{
            System.out.println("\nMENU");
            System.out.println("1.List food");
            System.out.println("2.sort from cheapset");
            System.out.println("3.sort from most expensive");
            System.out.println("press 4 for done");
            
            System.out.print("chose : ");
            chose1 = sc.nextInt();
            
            System.out.println("---------------------");
            
            switch(chose1){
                    case 1:
                        System.out.println("Menu \tPrice");
                        for (int i = 0; i < 5; i++) {
                            System.out.println(order[i]+"\t"+nominal[i]);
                        }
                    break;
                    case 2:
                        //(Assending) memakai algoritma bubble sort
                    
                        order2 = order;
                        nominal2 = nominal;
                        
                        for (int i = 0; i < 5; i++) {           //inti dari (bubble sort) with loop bersarang
                            for (int j = 0; j < 4; j++) {
                                if (nominal2[j] > nominal[j+1]) {   
                                    int temp = nominal2[j];       //teknik untuk menukar data
                                    nominal2[j] = nominal2[j+1];
                                    nominal2[j+1] = temp;
                                    
                                    //mengurutkan menu terkecil - terbesar
                                    String x = order2[j];
                                    order2[j] = order2[j+1];
                                    order2[j+1] = x;
                                }
                            }
                        }
                        System.out.println("sort from cheapset");
                        for (int i = 0; i < 5; i++) {
                            System.out.println(order2[i]+"\t"+nominal2[i]);
                        }
                        
                    break;
                    case 3:
                        order2 = order;
                        nominal2 = nominal;
                        for (int i = 0; i < 5; i++) {           //inti dari (bubble sort) with loop bersarang
                            for (int j = 0; j < 4; j++) {
                                if (nominal2[j] < nominal[j+1]) {   
                                    int temp = nominal2[j];       //teknik untuk menukar data
                                    nominal2[j] = nominal2[j+1];
                                    nominal2[j+1] = temp;
                                    
                                    //mengurutkan menu terkecil - terbesar
                                    String x = order2[j];
                                    order2[j] = order2[j+1];
                                    order2[j+1] = x;
                                }
                            }
                        }
                        System.out.println("sort from most expensive");
                        for (int i = 0; i < 5; i++) {
                            System.out.println(order2[i]+"\t"+nominal2[i]);
                        }
                        
                       
                    break;
                    case 4:
                        System.out.println("Program has done");
                    break;
            }
        } while(chose1 != 4);
    }
}
```
