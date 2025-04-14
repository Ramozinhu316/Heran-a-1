public abstract class Animal {
    protected String nome;
    protected int idade;

    public Animal(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    public abstract void emitirSom();

    public void info() {
        System.out.println(getClass().getSimpleName() + " chamado " + nome + ", idade " + idade);
    }
}

public abstract class Mamifero extends Animal {
    public Mamifero(String nome, int idade) {
        super(nome, idade);
    }

    public abstract void amamentar();
}

public abstract class Ave extends Animal {
    public Ave(String nome, int idade) {
        super(nome, idade);
    }

    public abstract void voar();
}

public abstract class Reptil extends Animal {
    public Reptil(String nome, int idade) {
        super(nome, idade);
    }

    public abstract void rastejar();
}

public class Cachorro extends Mamifero {
    public Cachorro(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Au au!");
    }

    @Override
    public void amamentar() {
        System.out.println("Amamenta os filhotes.");
    }
}

public class Gato extends Mamifero {
    public Gato(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Miau!");
    }

    @Override
    public void amamentar() {
        System.out.println("Amamenta os filhotes.");
    }
}

public class Tartaruga extends Reptil {
    public Tartaruga(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("...");
    }

    @Override
    public void rastejar() {
        System.out.println("Se move lentamente pelo chão.");
    }
}

public class Iguana extends Reptil {
    public Iguana(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Som baixo e rouco.");
    }

    @Override
    public void rastejar() {
        System.out.println("Rasteja pelas superfícies.");
    }
}
public class Galinha extends Ave {
    public Galinha(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Cocoricó!");
    }

    @Override
    public void voar() {
        System.out.println("Voa curtas distâncias.");
    }
}

public class Calopsita extends Ave {
    public Calopsita(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Assovia e imita sons.");
    }

    @Override
    public void voar() {
        System.out.println("Voa livremente em espaços abertos.");
    }
}

public class Pardal extends Ave {
    public Pardal(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Piu piu!");
    }

    @Override
    public void voar() {
        System.out.println("Voa rapidamente entre árvores.");
    }
}
public class Arara extends Ave {
    public Arara(String nome, int idade) {
        super(nome, idade);
    }

    @Override
    public void emitirSom() {
        System.out.println("Gritos altos!");
    }

    @Override
    public void voar() {
        System.out.println("Voa longas distâncias com asas largas.");
    }
}
public class Main {
    public static void main(String[] args) {
        Animal[] animais = {
            new Cachorro("Bolt", 5),
            new Gato("Mimi", 3),
            new Tartaruga("Lentinha", 50),
            new Iguana("Iggy", 4),
            new Galinha("Cocó", 2),
            new Calopsita("Luna", 1),
            new Pardal("Frajola", 1),
            new Arara("Ararinha Azul", 7)
        };

        for (Animal animal : animais) {
            animal.info();
            animal.emitirSom();

            if (animal instanceof Mamifero) {
                ((Mamifero) animal).amamentar();
            } else if (animal instanceof Ave) {
                ((Ave) animal).voar();
            } else if (animal instanceof Reptil) {
                ((Reptil) animal).rastejar();
            }

            System.out.println("-------------------------------");
        }
    }
}
