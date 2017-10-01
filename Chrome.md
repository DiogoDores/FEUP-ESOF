## Chrome Crash Link
Em setembro de 2015, Andris Atteka, investigador de segurança, reportou uma vulnerabilidade no popular browser Google Chrome, capaz de instantaneamente crashar o navegador. Para tal, bastaria acrescentar um carater nulo à string do URL e navegar para o link. Atteka, [no seu blog](https://andrisatteka.blogspot.pt/2015/09/a-simple-string-to-crash-google-chrome.html), admite não ter sido recompensado, sendo o achado considerado uma vulnerabilidade DoS (denial-of-service):  

> Unfortunately no reward was awarded as this was deemed to be only a denial-of-service vulnerability. Anyway, making secure software is much harder than finding issues in it. Thanks Google.

O URL que originalmente foi descoberto por explorar esta falha do browser era composto por 26 carateres, mas foi popularizada rapidamente uma versão mais curta - `http://a/%%30%30` - totalizando, assim, 16 carateres.

É de notar que este bug não só afetou o Google Chrome, como todas as aplicações baseadas em Chromium, incluindo outros browsers como o Opera e apps como o Atom e Slack.

Para tentar compreender a origem da vulnerabilidade, é necessário ter assente a noção de que, na sua essência, um computador é simplesmente uma cadeia interminável de zeros e uns. A certo ponto, o computador repara que uma determinada zona de memória corresponde, por exemplo, ao princípio do URL a que o utilizador pretende aceder. A leitura e condição de paragem reside em duas principais técnicas. Uma baseia-se em armazenar o número de carateres para ler e outra na leitura contínua até aterrar num carater `NULL`, um byte vazio.  
As percentagens no nosso URL malicioso significam um carater codificado. Ora, `%30` significa 0 - o número, não o carater nulo. Descodifiquemos agora o URL resultante. Em `http://a/%00`, `%00` é convertido para `NULL`. A função descodificadora marca o link como seguro para usar e o inevitável acontece.  

A vulnerabilidade é marcada como resolvida 5 dias após a sua descoberta, sendo o seu percurso desde a deteção até à resolução disponível para acompanhar no [fórum oficial de bugs do projeto Chromium](https://bugs.chromium.org/p/chromium/issues/detail?id=533361#c14).

Paulo Castro (pkasting), um dos desenvolvedores, lamenta:
> There are going to be crashes all over as a result of this. This is a mess.  

Como reportado por TheHackerNews.com,
> The issue appears to be small but is actually serious, as it is possible for any of your friends to tweet out the link in question, and crash all Chrome users whose Twitter timeline will load that link.

Esta vulnerabilidade haverá sido rapidamente reportada por websites de notícias como a WIRED, The Guardian e Daily Mail, apenas expandindo a escala do incidente.  
Tom Scott, web developer e previamente apresentador na Sky One relata as origens da vulnerabilidade em detalhe [no seu canal de YouTube](https://www.youtube.com/watch?v=0fw5Cyh21TE).  

Este incidente é similar ao de junho de 2015, que atormentou Skype, a popular plataforma especializada em conexões por voz e vídeo. Neste caso, bastaria um utilizador receber uma mensagem com o link `http://:` para desencadear um interminável loop de crashes incontroláveis antes que fosse possível a sua deleção. 

Adicionalmente, o paralelismo com a sequência de 75 bytes de unicode que desesperou utilizadores da Apple a maio de 2015 é evidente. Afetando desde iPhones até ao Apple Watch, esta string letal causaria a biblioteca CoreText a aceder a memória inválida, forçando o sistema operativo a terminar o processo atual. Assim, receber uma mensagem com este conteúdo resultaria no reboot instantâneo do dispositivo.  

Estas três vulnerabilidades têm em comum um descuido pelo tratamento de carateres por empresas de tecnologia multinacionais, tendo como consequências não tanto monetárias, mas sim sociais. Estes pontos fracos debilitam a experiência de utilizadores e geram frustração quando explorados por indivíduos maliciosos.

Entretanto, Sean Zhu desenvolveu [3030](https://github.com/szhu/3030), tirando vantagem do infame bug. O jogo tem como objetivo percorrer um labirinto de emojis, em que as paredes são hyperlinks para o URL problemático. Provando que mesmo de uma incómoda vulnerabilidade poderá advir alguma criatividade. 
