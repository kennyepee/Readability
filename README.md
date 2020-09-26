# Readability
package com.company;

import java.util.Scanner;


public class Main {
        public static void main(String args[]) {

            // Read paragraph from user
            Scanner keyboard = new Scanner(System.in);
            System.out.print("Enter text: ");
            String text = keyboard.nextLine();

            // Variable declaration
            int words = 1;
            int sentences = 0;
            int letters = 0;

            // Count Words
            for (int i  = 0; i  < text.length() - 1; i++){
                if ((text.charAt(i) == ' ') && (text.charAt(i + 1) != ' ')){
                    words++;}

            }
            for (char i : text.toCharArray()) {
 
                // Count Word Letters
                if (Character.isLetterOrDigit(i)) {
                    letters++;
                }
            }



            // Count Sentences
            sentences = text.split("[.]").length;

            // Calculate L value
            double L = ((double) letters / (double) words) * 100;

            // Calculate S value
            double S = ((double) sentences / (double) words) * 100;

            // Calculate Coleman Liau Index
            int grade = (int) Math.round(0.0588 * L - 0.296 * S - 15.8);



            System.out.println("Sentences: " + sentences);
            System.out.println("Words: " + words);
            System.out.println("Word letters: " + letters);
            if (grade < 1 ){
                System.out.println("Before Grade 1");
            }
            else if (grade >= 16){
                System.out.println("Grade 16+ ");
            }
            else
            System.out.println("Grade: " + grade);
        }
    }


