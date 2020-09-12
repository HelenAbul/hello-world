# hello-world
inicio
# Este é um fluxo de trabalho básico para ajudá-lo a começar com ações

nome : CI

# Controla quando a ação será executada. Aciona o fluxo de trabalho na solicitação push ou pull
# eventos, mas apenas para o branch $ default-branch
em :
  empurrar :
    branches : [$ default-branch]
  pull_request :
    branches : [$ default-branch]

# A execução de um fluxo de trabalho é composta por uma ou mais tarefas que podem ser executadas sequencialmente ou em paralelo
empregos :
  # Este fluxo de trabalho contém um único trabalho denominado "build"
  construir :
    # O tipo de executor em que o trabalho será executado
    roda em : ubuntu-mais recente

    # As etapas representam uma sequência de tarefas que serão executadas como parte do trabalho
    passos :
      # Faz o check-out de seu repositório em $ GITHUB_WORKSPACE, para que seu trabalho possa acessá-lo
      - usa : ações / checkout @ v2

      # Executa um único comando usando o shell do runners
      - name : executa um script de uma linha
        run : echo Hello, world!

      # Executa um conjunto de comandos usando o shell do runners
      - name : executa um script de várias linhas
        correr : |
          echo Adicionar outras ações para construir,
          teste de eco e implante seu projeto.
