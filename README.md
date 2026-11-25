# Biblioteca Digital — Trabalho IV (POO II)

Sistema desktop em **JavaFX** (Maven, JDK 17+) para gerenciamento de uma **Biblioteca Digital**, com cadastro, edição, remoção, busca, empréstimo e devolução de livros, persistência em arquivos CSV e aplicação de três padrões de projeto (**Singleton**, **Decorator** e **Observer**).

**Integrantes:** Kelly, Gabriel e Tauany  
**Disciplina:** Programação Orientada a Objetos II — Ciência da Computação (4º Período)  
**Professor:** Márcio Alves de Araújo

## Requisitos

- **Java JDK 17** ou superior.
- **IntelliJ IDEA** (com suporte Maven nativo) ou **Maven 3.8+**.

## Estrutura de Pacotes

- `br.com.bibliotecadigital.app` — ponto de entrada (`Main` e `BibliotecaApp`).
- `br.com.bibliotecadigital.model` — entidades (`Livro`, `Emprestimo`, `StatusLivro`).
- `br.com.bibliotecadigital.decorator` — padrão **Decorator** (`ItemBiblioteca`, `LivroBase`, `LivroDecorator`, `SeloDestaqueDecorator`, `AcessoOfflineDecorator`, `PrazoEstendidoDecorator`).
- `br.com.bibliotecadigital.observer` — padrão **Observer** (`BibliotecaSubject`, `BibliotecaObserver`, `EventoBiblioteca`).
- `br.com.bibliotecadigital.repository` — padrão **Singleton** e persistência CSV (`BibliotecaRepository`).
- `br.com.bibliotecadigital.controller` — regras de negócio, validações e Subject concreto (`BibliotecaController`).
- `br.com.bibliotecadigital.view` — interface JavaFX e Observers concretos (`TelaPrincipal`, `DialogoLivro`, `DialogoEmprestimo`, `PainelHistorico`).

## Como Executar no IntelliJ IDEA

1. Extraia o arquivo `biblioteca-digital.zip`.
2. No IntelliJ IDEA, clique em **File → Open...**, selecione o arquivo `pom.xml` dentro da pasta `biblioteca-digital` e escolha **Open as Project**.
3. Aguarde o Maven baixar o `javafx-controls` e concluir a indexação.
4. Abra `src/main/java/br/com/bibliotecadigital/app/Main.java` e clique no botão **Run** (triângulo verde).

## Como Executar pelo Terminal (Maven)

Na raiz da pasta `biblioteca-digital`:

```bash
mvn javafx:run
```

## Onde os Dados São Gravados

Os dados são persistidos automaticamente na pasta `dados/` na raiz do projeto:

- `dados/livros.csv` — catálogo de livros, status e recursos digitais (Decorator).
- `dados/emprestimos.csv` — histórico de empréstimos ativos e devolvidos.
