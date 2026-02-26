public class CuentaBancaria{

    String titular;
    double saldo;
    String numCuenta;

    public CuentaBancaria(String titular, double saldo,String numCuenta){

        this.titular = titular;
        this.saldo = saldo;
        this.numCuenta = numCuenta;
    }
    public CuentaBancaria(){

        this.titular = "Sin Nombre";
        this.saldo = 0;
        this.numCuenta = "0000";

    }

    public double depositar(double cantidad){

        saldo += cantidad;
        return saldo;

    }

    public double retirar(double cantidad){

        if(cantidad>saldo){

            System.out.println("saldo insuficiente");
            return saldo;

        }else{

            System.out.println("retirado correctamente");

        }
        saldo -= cantidad;
        return saldo;

    }

    public void consultarsaldo(){

        System.out.println("el saldo es de:  " + saldo);

    }

    public void mostrarinformacion(){

        System.out.println("titular: " + titular);
        System.out.println("numero de cuenta: " + numCuenta);
        System.out.println("saldo: " + saldo);

    }

} public class Main {

    public static void main(String[] args) {

        CuentaBancaria cuenta1 = new CuentaBancaria();

        CuentaBancaria cuenta2 = new CuentaBancaria("Carlos Perez", 500, "1234ABC");

        cuenta1.mostrarinformacion();

        System.out.println("");

        cuenta2.mostrarinformacion();

        System.out.println("");
        
        cuenta1.depositar(300);
        cuenta2.depositar(200);

        
        System.out.println("retirando 100 de cuenta1...");
        cuenta1.retirar(100);
        System.out.println("");

        
        System.out.println("retirando 1000 de cuenta2...");
        cuenta2.retirar(1000);

        System.out.println("");

        
        System.out.println("Informacion cuenta 1");
        cuenta1.mostrarinformacion();

        System.out.println("Informacion cuenta 2");
        cuenta2.mostrarinformacion();

    }
}
