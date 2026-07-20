# Fydelis Security Scanner
## Autor: Adiel Santos Fontes
O **Fydelis Security Scanner** é uma ferramenta de varredura de portas TCP, desenvolvida em Ruby, focada em velocidade, leveza e eficiência. Com suporte a multithreading e perfis de performance, ele é ideal para reconhecimento em testes de penetração e auditorias de rede.

## 🚀 Funcionalidades

*   **Multithreaded:** Varredura rápida usando filas de trabalho para processamento paralelo.
*   **Perfis de Velocidade:** Modos de execução configuráveis (`polite` a `insane`) para ajustar o ritmo do scan.
*   **Banner Grabbing:** Tenta identificar o serviço rodando na porta detectada.
*   **Versátil:** Suporte a intervalos de portas (`1-1000`), listas específicas (`22,80,443`) ou perfis pré-definidos.
*   **Exportação:** Salva resultados diretamente em arquivo de texto.
*   **Modo Verbose:** Exibe portas fechadas para auditorias detalhadas.

## 🛠 Instalação

Certifique-se de ter o [Ruby](https://www.ruby-lang.org/) instalado em seu sistema.

**bash
# Clone o repositório
git clone [https://github.com/SEU_USUARIO/fydelis-scanner.git](https://github.com/SEU_USUARIO/fydelis-scanner.git)

# Entre na pasta
cd fydelis-scanner

## 💻 Como Usar

# Scan básico de 2 portas
ruby -Ilib bin/fydelis.rb -t 127.0.0.1 -p 135,445

# Scan de intervalo 1-1000 com velocidade máxima
ruby -Ilib bin/fydelis.rb -t scanme.nmap.org -p 1-1000 --speed insane

# Scan das portas mais comuns com saída em arquivo
ruby -Ilib bin/fydelis.rb -t 192.168.1.1 --top-ports -o resultado.txt

# Scan modo educado (polite) com verbose
ruby -Ilib bin/fydelis.rb -t 10.0.0.1 -p 22,80,443,3306 --speed polite -v

# Ajuda
ruby -Ilib bin/fydelis.rb --help

## ⚙️ Opções Disponíveis
-t, --target	Define o IP ou Host alvo.
-p, --ports	Define as portas (ex: 80, 1-100, 22,80,443).
--speed	Perfil: insane, fast, normal, polite
-o, --output	Salva o resultado em um arquivo .txt
-v, --verbose	Exibe portas fechadas durante o scan
--threads	Define o número de threads (padrão: 50)
--top-ports	Escaneia apenas as portas mais comuns
