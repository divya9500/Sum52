# Sum52
Calculator
package Assessement4;
import java.util.Scanner;

public interface Interface {

  /*An interface in Java is a blueprint of a class.
   A Java interface contains static constants and abstract methods.
   The interface in Java is a mechanism to achieve abstraction.
   There can be only abstract methods in the Java interface,
   not the method body.*/
  /**/
  double  method(double n1,double n2,char c);


}





public abstract class Abstract {

    static double ans1;

  /*ABSTRACT
  *  abstraction is the process of hiding certain details and showing
     only essential information to the user.
  * A class which is declared with the abstract keyword is
    known as an abstract class in Java.
  * It can have abstract and non-abstract methods */
    public abstract double substraction(double n1, double n2);

    //METHOD OVERLOADING
    /*If a class has multiple methods having same name but different
     in parameters, it is known as Method Overloading. */
    public  double Addition(double n1,double n2)
    {
        ans1=n1+n2;
        return ans1;
    }
    public  double Addition(double n1,int n)
    {
        ans1=n1+n;
        return ans1;
    }

}


public class Main extends Abstract implements Interface {
  static  double ans;
  /*INHERITANCE
  * Inheritance in Java is a mechanism in which one object acquires
    all the properties and behaviors of a parent object.
   */

  /*METHOD OVERRINDING
  *  Overriding is a feature that allows a subclass or child class
   to provide a specific implementation of a method that is already
   provided by one of its super-classes or parent classes.
   */
  @Override
  public  double substraction(double n1,double n2){
      ans=n1-n2;
      return ans;
  }

  public double method(double n1, double n2,char c) {
      switch(c){

          case '*':
              ans=n1*n2;
              break;
          case '/':
              ans = n1 / n2;
              break;
          case '%':
              ans=n1%n2;
              break;
          case '^':
              ans= (int) Math.pow(n1,n2);
              break;
          default:
              System.exit(0);

      }
      return ans;
  }

  public static void main(String args[]) {

          Main ad = new Main();
          Scanner s = new Scanner(System.in);
          double n1 = s.nextDouble();

          for(int i=1;i<=50;i++) {
              String c1 = s.next();
              char c=c1.charAt(0);
              double n2 = s.nextDouble();

              int n= (int) n2;
              if(n2==n && c=='+'){
                  ad.Addition(n1,n);
                  ans=ans1;
              }
             else if(c=='+'){
                 ad. Addition(n1,n2);
                ans=ans1;
              }
              else if(c=='-'){
                  ad.substraction(n1,n2);
              }
              else {
                  ad.method(n1, n2, c);
              }
              System.out.println(ans);
              n1=ans;
          }
      }

  }

