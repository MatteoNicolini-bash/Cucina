// Classe base Piatto
abstract class Piatto {
    abstract void prepara();
}

// Classe Sugo
class Sugo {
    private String tipo;

    public Sugo(String tipo) {
        this.tipo = tipo;
    }

    public String getTipo() {
        return tipo;
    }
}

// Classe Primo che estende Piatto
class Primo extends Piatto {
    private Sugo sugo;

    public Primo(Sugo sugo) {
        this.sugo = sugo;
    }

    @Override
    void prepara() {
        System.out.println("Preparando primo con sugo: " + sugo.getTipo());
    }
}

// Classe Secondo che estende Piatto
class Secondo extends Piatto {
    @Override
    void prepara() {
        System.out.println("Preparando secondo piatto");
    }
}

// Classe Contorno che estende Piatto
class Contorno extends Piatto {
    @Override
    void prepara() {
        System.out.println("Preparando contorno");
    }
}

// Classe Dolce che estende Piatto
class Dolce extends Piatto {
    @Override
    void prepara() {
        System.out.println("Preparando dolce");
    }
}

// Classe Cuoco
class Cuoco {
    void preparaPiatto(Piatto piatto) {
        piatto.prepara();
    }
}

// Main per testare il sistema
public class Ristorante {
    public static void main(String[] args) {
        Sugo sugoBolognese = new Sugo("Bolognese");
        Primo primo = new Primo(sugoBolognese);
        Secondo secondo = new Secondo();
        Contorno contorno = new Contorno();
        Dolce dolce = new Dolce();

        Cuoco cuoco = new Cuoco();

        cuoco.preparaPiatto(primo);
        cuoco.preparaPiatto(secondo);
        cuoco.preparaPiatto(contorno);
        cuoco.preparaPiatto(dolce);
    }
}
