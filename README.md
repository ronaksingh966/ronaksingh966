- 👋 Hi, I’m @ronaksingh966
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
ronaksingh966/ronaksingh966 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import java.text.NumberFormat;
import java.text.SimpleDateFormat;
import java.util.Currency;
import java.util.Date;
import java.util.Locale;

public class SalarySlip {
    public static void main(String[] args) {
        // Locale and Currency setup
        Locale locale = new Locale("en", "IN");
        Currency currency = Currency.getInstance(locale);
        NumberFormat currencyFormatter = NumberFormat.getCurrencyInstance(locale);
        // Salary details
        double basicPay = 500000; // Example basic pay in INR
        double hra = 0.25 * basicPay;
        double da = 0.30 * basicPay;
        double ta = 0.20 * basicPay;
        double pf = 0.12 * basicPay;
        double grossSalary = basicPay + hra + da + ta;
      // Calculate TAX based on the basic pay slabs
        double tax = calculateTax(basicPay);
        double netSalary = grossSalary - (pf + tax);
        // Format date
        SimpleDateFormat dateFormat = new SimpleDateFormat("MMMM yyyy", locale);
        String date = dateFormat.format(new Date());
       // Output salary slip
        System.out.println("Salary Slip for " + date);
        System.out.println("--------------------------------------------------");
        System.out.println("Basic Pay: " + currencyFormatter.format(basicPay));
        System.out.println("HRA (25%): " + currencyFormatter.format(hra));
        System.out.println("DA (30%): " + currencyFormatter.format(da));
        System.out.println("TA (20%): " + currencyFormatter.format(ta));
        System.out.println("PF (12%): " + currencyFormatter.format(pf));
        System.out.println("Gross Salary: " + currencyFormatter.format(grossSalary));
        System.out.println("--------------------------------------------------");
        System.out.println("Tax Deduction: " + currencyFormatter.format(tax));
        System.out.println("Net Salary: " + currencyFormatter.format(netSalary));
        System.out.println("--------------------------------------------------");
    }

    private static double calculateTax(double basicPay) {
        if (basicPay <= 320000) {
            return 0;
        } else if (basicPay <= 450000) {
            return 0.12 * basicPay;
        } else if (basicPay <= 699000) {
            return 0.15 * basicPay;
        } else {
            return 0.20 * basicPay;
 }
}
}

