
# A portfolio consisting of all the work I have done related to the field of Information systems. 

# [Assistant Project Manager: Project Whyspots](https://whyspot.vercel.app/)

* Provided assistance in the planning, execution and implementation of the project.
* Scheduling meetings, keeping track of deliverables along with tracking and reporting project progress.
* Performed tasks assigned by the Project Manager in a timely manner.
* Created graphic SVG assets for the developers to use (logos, icons, backgrounds etc)


# [Research Paper on Ensemble Methods in Machine Learning](https://github.com/zain123d/Zain_portfolio/files/6274761/Ensemble.Methods.By.Zain.Ul.Abiden.pdf)

* Research Paper written as part of a Data Science class for my Master of Science in Information Systems program at University of Texas at Arlington
* Topic: Ensemble Methods in Machine Learning.
* Diving deep into understanding the fundemanetals of the methodology.
* Example on how to use Ensemble Method provided in the paper using Python coding.

## Resources Used:
* Python version 3.7
* Jupyter Notebook
* Sources sited at the end of the PDF
* Packages used: IPython.display, numpy, pandas, sklearn and graphviz.


# Project 1

# [Data Visualization using Python in Jupyter Notebook for ChocolateBomberDFW](https://github.com/zain123d/Zain_portfolio/files/6275523/chocolatebomberdfw.-.most.common.payment.type.pdf)
 
* Imported Excel sheet with customer information that included item ordered, amount paid, type of medium used for paying, address etc.
* Cleaned out unnecessary columns from the dataset and only kept Amount paid and Type of medium used.
* Grouped the amount paid based on type of medium used to get a sum of total amount for each type.
* Using matplotlib, plotted the data in a Pie chart to display percentage of amount for each type of medium.
* Visualized most common type of medium used for payment. 


## Resources used:
* Python Version: 3.9
* Packages used: pandas, numpy and matplotlib

# Project 2

# [Foreign Direct Investment Visualization using Tableau](https://public.tableau.com/profile/zain.ul.abiden#!/vizhome/FDICaseStudy-Zain/Dashboard1) 
* Imported CSV dataset into Tableau 

**Case Study questions included:**

1. Which sector receives the maximum and minimum direct funding for a given year?
2. Is there a trend for direct investments for individual sector?
3. In what fashion can the sectors be group for comparison?
4. Which sectors reported the highest growth and decline in the past 5 years?
5. Which sector reported the most variation overall?
6. What is the proportion of investment between sectors from the FDI perspective?
7. Are there any specific clusters present in the data?
8. Can we forecast the trend for the following year?

## Resources Used:
* Tableau Public; Version 2021.1
* FDI Dataset for the years 2000 till 2016

# Project 3

# [Machine Learning - Prediction Models (Class Assignment)](https://github.com/zain123d/Zain_portfolio/files/6274632/Machine.Learning.Assignment.3.-.Zain.Ul.Abiden.pdf)

* Used a Diabete.csv dataset to create prediction models using Decision Tree, Logistic Regression, Support Vector Machine and Random Forest.
* Calculated AUC (Area Under the Curve) score for the models and found Logistic Regression in this case was the better option for our prediction model. 
* Used the same dataset to create visualization using:
 1. K-means to Cluster the points
 2. Spectral Clustering 
 3. DBSCAN

* Image Manipulation using Python.
* Reduced the colors in the image to 64, 16 and 8 colors. 

* Imported a dataset "FIFA20" which contained images of famous soccer players.
* Using PCA method, reshaped the data from (200,230400) to (200,200).
* Used elbow and silhouette methods to find the best number of clusters for the images.
* Visualized the clusters using inverse_transform() function in PCA.

## Resources used:
* Python version 3.7
* Jupyter Notebook
* Packages used: pandas, nupmy, sklearn, matplotlib, scipy and PIL 


# Project 4

# Mortgage Calculator using Java Programming

* Mortgage calculator along with a schedule of payments 
* Written as part of course named Fundamental Java Programming taught by Mosh Hamedani from codewithmosh.com
* Code mentioned below:

package com.zain;
import java.text.NumberFormat;
import java.util.Scanner;
public class Main {

    final static byte  monthsInYear = 12;
    final static byte  percent = 100;

    public static void main(String[] args) {
        //Principal input in range 1K to 1M
        int principal = (int) readNumber("Principal: ", 1000, 100_000_000);
        //Down payment input not lower than 1K and not higher than or equal to Principal
        int downPayment = (int) readNumber("What is your down payment?: ", 1000, 500_000);
        //Annual interest input not higher than 30%
        float annualInterest = (float) readNumber("Annual Interest rate: ", 1, 30);
        //Number of payments and number of years no less than 1 no higher than 30
        byte years = (byte) readNumber("Period in years: ", 1 , 30);
        //Mortgage calculation
        double mortgage = calculateMortgage(principal, downPayment, annualInterest, years);
        String mortgageFormatted = NumberFormat.getCurrencyInstance().format(mortgage);
        System.out.println("MORTGAGE\n--------\nMonthly Payments: " + "\n" + mortgageFormatted);
        System.out.println();

        printPaymentSchedule(principal, downPayment, annualInterest, years);
    }

    private static void printPaymentSchedule(int principal, int downPayment, float annualInterest, byte years) {
        System.out.println("Payment schedule\n------------");
        for (short month = 1; month <= years * monthsInYear; month++) {
            double balance = calculateBalance(principal, downPayment, annualInterest, years, month);
            System.out.println(NumberFormat.getCurrencyInstance().format(balance));
        }
    }

    public static double readNumber(String prompt, double min, double max){
        Scanner scanner = new Scanner(System.in);
        double value;
        while (true) {
            System.out.print(prompt);
            value = scanner.nextFloat();
            if (value >= min && value <= max)
                break;
            System.out.println("Enter a value between " + min + "and " + max);
        }
        return value;
    }
    public static double calculateMortgage(
            int principal,
            int downPayment,
            float annualInterest,
            byte years) {

        short numberOfPayments = (short)(years * monthsInYear);
        float monthlyInterest = annualInterest / percent / monthsInYear;
        return (principal - downPayment) * (monthlyInterest * Math.pow(1 + monthlyInterest, numberOfPayments)) / (Math.pow(1 + monthlyInterest, numberOfPayments) - 1);
    }
    public static double calculateBalance (
            int principal,
            int downPayment,
            float annualInterest,
            byte years,
            short numberOfPaymentsMade) {
        final byte monthsInYear = 12;
        final byte percent = 100;

        short numberOfPayments = (short)(years * monthsInYear);
        float monthlyInterest = annualInterest / percent / monthsInYear;

        return (principal-downPayment)
                * (Math.pow(1+monthlyInterest, numberOfPayments) - Math.pow(1+monthlyInterest, numberOfPaymentsMade)) /
                (Math.pow(1+monthlyInterest,numberOfPayments)-1);
    }
}


