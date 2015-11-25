/* Insert Witty Team Name Here - Ling Cheng and Adam McKoy
   APCS1 pd10
   HW37 - Rational Equality
   2015-11-25 */

public class Rational {
    private int numerator;
    private int denominator;
    public int getNum() {
	return numerator;
    }
    public int getDenom() {
	return denominator;
    }
    public Rational() {
	numerator = 0;
	denominator = 1;
    }
    public Rational(int n,int d) { //makes sure the Rational doesn't have a denom of 0
	numerator = n;
	if (d!= 0) {
	    denominator = d;
	}
	else {
	    System.out.println("Naw. Undefined. Denominator set to 1.");
	    denominator = 1;
	}
    }
    public double floatValue() { //makes it a double so it is more precise
	return (double)numerator / denominator;
    }

    public String toString() { //this is the way that fractions are usually written out
	return numerator + "/" + denominator;
    }
    public void multiply(Rational i) { //multiplies the numerators together as well as denominators
	numerator *= i.getNum();
	denominator *= i.getDenom();
    }
    public void divide(Rational i) { //makes sure i is not equal to zero and multiplies by i's reciprocal
	if (i.getNum() == 0){
	    System.out.println("Y u divide by zero, m8?");
	    return;
	}
	Rational recipI = new Rational(i.getDenom(),i.getNum());
	multiply(recipI);
    }
    public void add(Rational i){
	numerator = getNum() * i.getDenom() + getDenom() * i.getNum();
	denominator = getDenom() * i.getDenom();
    }
    public void subtract(Rational i){
	add(new Rational(-i.getNum(),i.getDenom()));
    }
    public int gcd() {
	return gcd(numerator,denominator);
    }
    public static int gcd(int num, int denom) {
        if (denom > num){
            return gcd(denom, num);
        } else{
            while((num % denom) != 0){
                int holder = num;
                num = denom;
                denom = (holder % denom);
            }
	    return denom;
	}
    }
    public void reduce() {
	int gcd = gcd();
	denominator /= gcd;
	numerator /= gcd;
    }
    public int compareTo(Rational i){
	int difference = getNum() * i.getDenom() - getDenom() * i.getNum();
	if (difference > 0){
	    return 1;
	} else if(difference < 0){
	    return -1;
	} else{
	    return 0;
	}


    }
    public boolean equals(Rational i){
	return compareTo(i) == 0;
    }
    public static void main(String[] args){
	Rational rat1 = new Rational();
	Rational rat2 = new Rational(1,2);
	Rational rat3 = new Rational(5,3);
	Rational rat5 = new Rational(3,4);
	Rational rat6 = new Rational(3,4);
	System.out.println(rat1 + " = " + rat1.floatValue());
	System.out.println(rat2);
	rat2.multiply(rat3); //5/6
	System.out.println(rat2);
	rat3.divide(rat2); //2 = 30/15
	System.out.println(rat3);
	rat3.divide(rat1);
	System.out.println(rat3);
	Rational rat4 = new Rational(1,2);
	rat4.add(rat2); //8/6
	System.out.println(rat4);
	rat4.subtract(rat2); //1/2
	System.out.println(rat4);
	System.out.println( gcd(12,16) );
	System.out.println( rat4.gcd() );
	rat4.reduce();
	System.out.println(rat4);
	System.out.println( rat4.compareTo(rat2) );
	System.out.println( rat4.compareTo(rat3) );
	System.out.println( rat4.compareTo(rat1) );
	System.out.println( rat4.compareTo(rat4) );
	System.out.println( rat5.equals(rat6) );
	System.out.println( rat5.equals(rat1) );
    }
}