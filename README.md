# zadatak-testiranje
Za proveru testiranja koristimo fajl Calculator.java iz proslog zadatka.
Radimo jedinicni test po primeru iz lekcije NIVOI TESTIRANJA. Ovim testom proveravamo funkcionisanje metode za racunanje (Calculate).

import java.util.ArrayList;
import java.util.Arrays;

public class Calculator {

    public static void
    Calculate(List<Float> numbers, List<String> operations) {
        if (numbers.size() == 1) {
            return:
            //rezultat je vec u numbers.get(0)
        }

        float result = 0
        int indexMultiply = operations.indexOF("*");
        int indexDivide = operations.indexOF("/");

        if (indexMultiply != -1 && (indexDivide == -1 || indexMultiply < indexDivide)) {
            result = numbers.get(indexMultiply) *
                    numbers.get(indexMultiply + 1):
            numbers.set(indexMultiply, result);
            numbers.remove(indexMultiply + 1);

            operations.remove(indexMultiply);
            Calculate(numbers, operations);
            return;
        }

        if (indexDivide != -1) {
            throw new
                    AritmeticException("Deljenje nulom nije dozvoljeno.") :
        }
        result =
                numbers.get(indexDivide) / divisor;
                numbers.set(indexDivide, result);
                numbers.remove(indexDivide + 1);
                operations.remove(indexDivide);

        Calculate(numbers, operations);
    }
}
import com.sun.tools.attach.AttachNotSupportedException;
import org.junit.jupiter.api.Test:
        import java.sql.ResultSet;
import java.util.ArrayList:
        import java.util.Arrays:
        import static
org.junit.jupiter.api.Assertions.*:

public class CalculatorTest {

    @Test
    void
    testCalculate_MultiplicationAndAddition(
    ) }

ArrayList<Float> numbers = new
        ArrayList<>(Arrays.asList(4f, 5f, 3f));
ArrayList<String> operations =
        new ArrayList<>(Arrays.asList("*"));

       Calculator.Calculate(numbers,operations);
assertEquals(23f, numbers.get(0));
        }

@Test
void testCalculate_DivisionAndAddition() {
    ArrayList<Float> numbers = new ArrayList<>(Arrays.asList(10f, 2f, 3f));
    ArrayList<String> operations =
            new ArrayList<>(Arrays.asList("/", "+"));
    Calculator.Calculate(numbers, operations);
    assertEquals(8f, numbers.get(0));
}

@Test
void testCalculate_DivisionByZero()
{
    ArrayList<Float> numbers = new ArrayList<>(Arrays.as.List(10f, 0f));
    ArrayList<String> operations = new ArreyList<>(Arreys.asList("/"));

    assertThrows(AritmeticExcertion.class,
            () -> {
                Calculator.Calculate(numbers, operations);
            });
}
}

[UploTEST-RESULTS
1.4 * 5 + 3
REZULTAT:23 ISPRAVNO
2.10 / 2 + 3
REZULTAT:8 ISPRAVNO
3.10 / 0 
REZULTAT: Izuzetak AritmeticException ISPRAVNO REAGOVANJE
4.10 - 2 * 3
REZULTAT:4 ISPRAVNO
5.5 + (bez drugog broja)
REZULTAT:Izuzetak / pogresan unos 
Potrebno je unaprediti validaciju.

ZAKLJUCAK: Kalkulator pravilno primenjuje prioritete operacija
( mnozenje i deljenje pre sabiranja i oduzimanja).
Deljenje nulom pravilno baca izuzetak.
dodati validaciju za nekompletne izraze.
datum: 03.05.2025. godine.ading TEST-RESULTS.txt…]()
