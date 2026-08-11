# Guia gestió d'espais d'emmagatzematge a Windows

Els espais d'emmagatzematge van aparèixer a partir de Windows 8 i Windows Server 2012, i permeten crear volums virtuals amb redundància i tolerància a fallades. Aquests espais d'emmagatzematge poden ser configurats amb diferents nivells de redundància i són molt més flexibles que els sistemes RAID tradicionals, ja que per exemple, permeten anar afegint emmagzetmatge addicional a mesura que les necessitats de l'organització creixen.

Hi ha dos conceptes que no cal confondre:

- **Grup emmagatzematge**: és un conjunt de discs durs físics que s'utilitzen per crear espais d'emmagatzematge, el podem entendre com un contenidor de discos.

- **Espai d'emmagatzematge**: és un volum virtual creat a partir d'un grup d'emmagatzematge, el podem entendre com un disc dur virtual que inclou algun tipus de redundància. Un grup d'emmagatzematge pot contenir diversos espais d'emmagatzematge, i un espai d'emmagatzematge pot utilitzar diversos discs durs físics.

Els espais d'emmagatzematge permeten crear volums virtuals amb diferents nivells de redundància, com ara:

- **Simple**: sense redundància, similar a un RAID 0. El principal avantatge és disposar d'un volum que pot ser més gran que qualsevol dels discs durs físics que el componen. El principal inconvenient és que si un disc dur falla, es perd tota la informació.
- **Mirall doble**: amb redundància, similar a un RAID 1.
- **Paritat**: amb redundància, similar a un RAID 5, ja que utilitza un disc dur per emmagatzemar la informació de paritat. Requereix de tres discos.
- **Mirall triple**: amb redundància, similar a un RAID 1, però amb més tolerància a fallades, ja que manté tres còpies de la informació. Requereix de cinc discos i es basa a la tecnologia de "cluster quantum" [2](https://www.techtarget.com/whatis/definition/cluster-quorum-disk)



### Administrador de discs

El primer pas un cop iniciem la màquina virtual és anar al "Administrador de discos", en entrar ens avisarà que detecta tres discos sense inicialitzar. Els podem inicialitzar amb el sistema de fitxers NTFS i amb l'estil de partició MBR.

![Administrador de discos](./media/imagen01.png)

### Administració d'espais d'emmagatzematge

A "Configuració" hi ha l'eina "Administració d'espais d'emmagatzematge"

![Administració d'espais d'emmagatzematge](./media/imagen02.png)

Aquí és es creen els grups de volums i els espais.

### Espai Simple

1. Creem un grup d'emmagatzematge i afegim **dos** dels tres discos durs a aquest grup.
2. Definim un espai **simple** i definiu un espai superior al disponible del grup d'emmagatzematge. Assignem un nom i una lletra de unitat a l'espai.
3. Afegiu ara el tercer disc al grup d'emmagatzematge i observeu com podeu 
