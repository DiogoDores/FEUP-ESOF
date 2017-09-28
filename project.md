## Chrome Crash Link
Em Setembro de 2015, Andris Atteka reportou uma vulnerabilidade no popular browser Google Chrome, capaz de instantaneamente crashar o navegador. Para tal, bastaria acrescentar um carater nulo à string do URL. Atteka, no seu blog, admite não ter sido recompensado, sendo o achado considerado uma vulnerabilidade DoS (Denial-of-service).  
O URL que originalmente foi descoberto por explorar esta falha do browser era composto por 26 carateres, mas foi popularizada rapidamente uma versão mais curta - `http://a/%%30%30` - totalizando, assim, 16 carateres.


Para tentar compreender a origem da vulnerabilidade, é necessário ter assente a noção de que, na sua essência, um computador é simplesmente uma cadeia interminável de zeros e uns. A certo ponto, o computador repara que uma determinada zona de memória corresponde, por exemplo, ao princípio do URL a que o utilizador pretende aceder. A leitura e condição de paragem reside em duas principais técnicas. Uma baseia-se em armazenar o número de carateres para ler e outra na leitura contínua até aterrar num carater `NULL`, um byte vazio.  
As percentagens no nosso URL malicioso significam um carater codificado. Ora, `%30` significa 0 - o número, não o carater nulo. Descodifiquemos agora o URL resultante. Em `http://a/%00`, `%00` é convertido para `NULL`. A função descodificadora marca o link como seguro para usar e o inevitável acontece.  
Um contribuidor do Chromium lamenta:
> There are going to be crashes all over as a result of this. This is a mess.  

Esta vulnerabilidade haverá sido rapidamente reportada por websites de notícias como a WIRED e The Guardian, apenas expandindo a escala do incidente.
