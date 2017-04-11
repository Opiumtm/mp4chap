*MP4 chapter extraction utility*

Simple portable c# library (.net, windows runtime, windows phone) for a chapter support in mpeg audio files.

Sample usage:

```c#
using System;
using System.IO;
using Mp4Chapters;

namespace TestChapters
{
    class Program
    {
        static void Main(string[] args)
        {
            using (var str = File.OpenRead(args[0]))
            {
                var extractor = new ChapterExtractor(new StreamWrapper(str));
                Console.WriteLine(extractor.IsMp4a());
                extractor.Run();
                foreach (var c in extractor.Chapters ?? new ChapterInfo[0])
                {
                    Console.WriteLine("{0} -> {1}", c.Time, c.Name);
                }
            }
        }
    }
}
```

*Nuget package*

https://www.nuget.org/packages/mp4chap/
```
PM> Install-Package mp4chap 
```
