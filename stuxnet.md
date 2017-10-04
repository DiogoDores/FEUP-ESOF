
# O *worm Stuxnet*

<p align = "justify">
<i>Stuxnet</i> é um <i>worm</i> utilizado para monitorizar e controlar instalações industriais de larga escala. Foi inicialmente descoberto a Junho de 2010 pela empresa bielorrussa VirusBlokAda, numa central nuclear iraniana. Foi o primeiro <i>malware</i> que conseguiu interagir com o mundo físico e não apenas danificar o equipamento infetado.<sup><a href = https://uk.norton.com/stuxnet>[1]</a></sup>
</p>

### Como funciona

<p align = "justify">
Este worm propaga-se maioritariamente por <i>pen drives</i>, permitindo-lhe facilmente infetar dispositivos e redes que não estão conectados à <i>Internet</i>. O <i>malware</i> explorava algumas vulnerabilidades (também chamadas de <i>zero-days</i>) de um método que o sistema operativo <i>Windows</i> usava para lidar com os ficheiros de atalho (ficheiros .lnk). Normalmente, este tipo de ficheiros é inofensivo a não ser que um utilizador execute esse ficheiro. Porém, a empresa bielorrusa descobriu que os ficheiros na origem do <i>worm</i> eram capazes de se executar automaticamente, se fossem guardados numa <i>pen drive</i> que fosse, mais tarde, aberta pelo <i>Windows Explorer</i>.<sup><a href = https://www.forbes.com/2010/10/06/iran-nuclear-computer-technology-security-stuxnet-worm.html>[2]</a></sup><b> Sergey Ulasen</b>, chefe da equipa que descobriu a existência deste <i>malware</i>, num <a href=http://anti-virus.by/en/tempo.shtml> comunicado</a>, explica:
</p>

> “[...] You just have to open infected USB storage device using (Windows) Explorer or any other file manager which can display icons (for i.e. Total Commander) to infect your Operating System and allow execution of the malware. [...]”

<p align = "justify">
O <i>Stuxnet</i> instala ainda duas drivers (<i>mrxnet.sys</i> e <i>mrxcls.sys</i>). Estes ficheiros, também chamados de <i>rootkits</i>, eram utilizados de modo a tornar o <i>malware</i> invisível ao utilizador. A equipa de Ulasen descobriu também que estes ficheiros possuiam a assinatura digital da <a href=http://www.realtek.com/> Realtek</a>.
</p>

<p align = "justify">
No entanto, o <i>worm</i> não afeta realmente os computadores infetados. O que este faz, é procurar um determinado modelo de um <i>Programmable Logic Controller</i> (PLC), manufaturado pela <a href=https://www.siemens.com/global/en/home.html> Siemens</a>.
</p>

Estes PLC's são pequenos sistemas de controlo industrial que executam todo o tipo de processos automatizados.<sup><a href = https://krebsonsecurity.com/2010/07/experts-warn-of-new-windows-shortcut-flaw/#more-4045>[3]</a></sup> 

### Sistemas afetados e consequências

<p align = "justify">
O <i>worm</i> foi inicialmente utilizado para prejudicar e parar o funcionamento de centrais nucleares iranianas responsáveis pelo enriquecimento de urânio. O <i>Stuxnet</i>, ao aceder aos PLC's, conseguia controlar as centrifugadoras da central e, aumentando a sua velocidade de rotação, destrui-las, impossibilitando a sua posterior utilização.
 </p>
  
<p align="center">
 <img src="http://www.extremetech.com/wp-content/uploads/2015/03/Stuxnet.jpg"  alt = "Esquema sumário da propagação do worm" height = "415" width = "650">
  <br>
  Fig. 1 - Esquema sumário da propagação do <i>worm</i>
  <sup><a href = http://www.extremetech.com/wp-content/uploads/2015/03/Stuxnet.jpg>[4]</a></sup>
</p>  

<p align="center">
Estima-se que cerca de 1000 centrifugadoras foram afetadas pelo <i>Stuxnet</i>. No entanto, o governo iraniano não lançou nenhuma informação acerca dos danos  causados ou do custo dos mesmos, sendo impossível estimar valores com certeza.
</p>

<p align="center">
 <img src="https://media.wired.com/photos/593238c69be5e55af6c2398e/master/w_532,c_limit/Ahmadinejad-at-Natanz.jpg"  alt = "Presidente iraniano Mahmoud Ahmadinejad durante uma visita às centrifugadoras em Natanz (2008)" height = "415" width = "650">
  <br>
  Fig. 2 - Presidente iraniano, Mahmoud Ahmadinejad, durante uma visita às centrifugadoras em Natanz (2008)
  <sup><a href = https://media.wired.com/photos/593238c69be5e55af6c2398e/master/w_532,c_limit/Ahmadinejad-at-Natanz.jpg>[5]</a></sup>
</p>

<p align="justify">
  O <i>worm</i> conseguiu ainda afetar outros países. Contudo, como o <i>Stuxnet</i> necessita de condições muito específicas para funcionar, em muitos dispositivos não surtiu qualquer efeito, tendo ficado inerte. Ainda assim, ao longo de vários meses, foram sendo descobertos milhares de outros computadores infetados, tal como o gráfico abaixo ilustra.
</p>

<p align="center">
 <img src="http://www.symantec.com/content/en/us/global/images/threat_writeups/2010-071400-3123-99.1.jpg"  alt = "computadores infetados" height = "415" width = "650">
  <br>
  Fig. 3 - Percentagem de computadores afetados pelo <i>Stuxnet</i> globalmente
  <sup><a href = http://www.symantec.com/content/en/us/global/images/threat_writeups/2010-071400-3123-99.1.jpg>[6]</a></sup>
</p>

### Conclusão

<p align = "justify">
Embora todas estas falhas, tanto da Microsoft como da Siemens, já tenham sido corrigidas em updates posteriores, o <i>Stuxnet</i> não pode ser ignorado. Existem <i>online</i> várias versões deste <i>worm</i>, conseguindo qualquer pessoa (com os fundos e conhecimentos suficientes) alterar este vírus e utilizá-lo a uma escala bastante mais larga, podendo as consequências deste ataque ser devastadoras. No vídeo abaixo está sucintamente resumido o ataque à central nuclear e o que este pode ter desencadeado.
</p>

<p align = "center">
<a href="http://www.youtube.com/watch?feature=player_embedded&v=7g0pi4J8auQ" target="_blank">
<img src="http://img.youtube.com/vi/7g0pi4J8auQ/0.jpg" alt="stuxnetvideo"/></a>
 <br>
  STUXNET: The Virus that Almost Started WW3
</p>

