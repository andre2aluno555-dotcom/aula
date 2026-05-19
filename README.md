package familia;

import java.time.LocalDate;

public class Pessoa {

    private String nome;
    private LocalDate dataNascimento;

    public Pessoa(String nome, LocalDate dataNascimento) {
        setNome(nome);
        setDataNascimento(dataNascimento);
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        if (nome == null || nome.isBlank()) {
            throw new IllegalArgumentException("Nome inválido");
        }
        this.nome = nome;
    }

    public LocalDate getDataNascimento() {
        return dataNascimento;
    }

    public void setDataNascimento(LocalDate dataNascimento) {
        if (dataNascimento == null || dataNascimento.isAfter(LocalDate.now())) {
            throw new IllegalArgumentException("Data de nascimento inválida");
        }
        this.dataNascimento = dataNascimento;
    }
    public String toString() {
        return "Pessoa [nome=" + nome + ", dataNascimento=" + dataNascimento + "]";
    }
public class ExemploMain {
    public static void main(String[] args) {
        Pessoa p1 = new Pessoa("Maria", LocalDate.of(1980, 5, 10));
        Pessoa p2 = new Pessoa("João", LocalDate.of(1975, 3, 20));
        Pessoa p3 = new Pessoa("Ana", LocalDate.of(1990, 8, 15));

        Familia familia = new Familia();
        familia.adicionarPessoa(p1);
        familia.adicionarPessoa(p2);
        familia.adicionarPessoa(p3);

        System.out.println("Pessoa mais velha: " + familia.encontrarPessoaMaisVelha());
    }
}
}
