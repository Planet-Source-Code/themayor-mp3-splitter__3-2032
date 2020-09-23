<div align="center">

## mp3 splitter


</div>

### Description

I had a problem when downloading mp3's. With no cd burner or network i couldn't get my mp3's to a friends house. So i made an mp3 splitter. A normal 4.0 mb song could fit on three disks. but it this splitter can support up to 30 mb's. I doubt any song is longer than that
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[theMayor](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/themayor.md)
**Level**          |Beginner
**User Rating**    |3.7 (11 globes from 3 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/themayor-mp3-splitter__3-2032/archive/master.zip)





### Source Code

```
#include <stdio.h>
#include <iostream.h>
#include <fstream.h>
#include <string>
int main(int argc, char *argv[])
{
 int filesize=140000;// This is approximatley 1.4 mb's. Change this to fit your needs
 char * charachters[]={"a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z"};
 int fname=0;
 FILE *in;
 FILE * splitted;
 ofstream bat ("combine.bat");
 int bcounter=0;
 unsigned int filenum;
 unsigned char ch;
 if(argc == 1)
 {
  cout << "\nneed file\n";
  return 0;
  }
 in = fopen(argv[1], "rb");
 bat << "copy /b a";
 ch = (char) getc(in);
 splitted=fopen(charachters[fname],"wb");
 for(filenum=0; !feof(in); filenum++)
 {
  if (filenum%filesize==0 && filenum!=0)
  {
   fclose(splitted);
   fname++;
   bat << "+"<<charachters[fname];
   splitted=fopen(charachters[fname],"wb");
  }
  fputc(ch,splitted);
  cout << ch;
  ch = (char) getc(in);
  }
bat << " "<<argv[1];
bat.close();
fclose(in);
fclose(splitted);
return 1;
}
```

