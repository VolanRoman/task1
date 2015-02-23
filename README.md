//Ввести с консоли дату. Сравнить ее с текущей датой в
//системе. Вывести отличающиеся части (год, месяц) на
//экран.

import java.util.*;
import java.text.*;

public class HomeWork_6 {
    public static void main (String [] args) {
        //1.
        // вводим дату в заданном формате
        Scanner sc = new Scanner (System.in);
        SimpleDateFormat sdf = new SimpleDateFormat ("dd.MM.yyyy");

        System.out.println ("Введите дату в формате dd.MM.yyyy: ");
        String s = sc.nextLine();

        // сравниваем даты
        try {
            Calendar cl1 = Calendar.getInstance ();
            Date dt = sdf.parse (s);
            Calendar cl2 = Calendar.getInstance();
            cl2.setTime(dt);

            if (cl1.get(cl1.DATE) != cl2.get(cl2.DATE)) {
                System.out.println ("Дата в системе: " + cl1.get(cl1.DATE) +
                        " Введенная дата: " + cl2.get(cl2.DATE));
            }
            else System.out.println ("Введенная дата совпадает с системной");

            if (cl1.get(cl1.MONTH)  != cl2.get(cl2.MONTH)) {
                System.out.println ("Месяц в системе: " + (cl1.get(cl1.MONTH)+1) +
                        " Введенный месяц: " + (cl2.get(cl2.MONTH)+1));
            }
            else System.out.println ("Введенный месяц совпадает с системным");

            if (cl1.get(cl1.YEAR) != cl2.get(cl2.YEAR)) {
                System.out.println ("Год в системе: " + (cl1.get(cl1.YEAR)) +
                        " Введенный год: " + (cl2.get(cl2.YEAR)));
            }
            else System.out.println ("Введенный год совпадает с системным");

        } catch (ParseException exc) {
            System.out.println("Вы ввели неверную дату");
        }
        
    }
}
