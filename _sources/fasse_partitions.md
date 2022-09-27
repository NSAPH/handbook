## FASSE Partitions

If your FASSE session has crashed due to insufficient memory, it may be due to using the incorrect partition. A partition is a queue for your work, and FASSE has several of these, each with different sizes and restrictions. In RStudio, you can select which partition you would like to use before you start your session. Below you can see where to type the name of the desired partition. 


<img width="1422" alt="Screen Shot 2022-08-23 at 5 15 37 PM" src="https://user-images.githubusercontent.com/89894104/186270037-33d2abc7-523d-4b22-b714-0c366d124f63.png">



Sometimes the data you are working with can require a very large amount of memory, such as individual data from Medicare enrollment files. If you are anticipating using a lot of memory, you should request from the fasse_bigmem partition. 

```{note}
To view FASSE partions and learn more, see [the official FASSE documentation](https://docs.rc.fas.harvard.edu/kb/fasse/#articleTOC_15).
```

For your convenience, the list is also below, updated August 2022:
|Partition	|Number of Nodes	|Cores per Node	|CPU Core Types|	Mem per Node (GB)|	Time Limit	|Max Jobs	|Max Cores	|MPI Suitable?	|GPU Capable?|
|---        |------           |----           | ------       |  -----            | -----        | --      | ---       | ----          | ----- |
|fasse	|42	|48	|Intel "Cascade Lake"	|184	|7 days	|none	|none	|yes	|No|
|fasse_bigmem	|6	|64	|Intel "Ice Lake"	|499	|7 days|	none	|none	|yes|	No|
|fasse_gpu	|4	|32	|Intel| "Cascade Lake"|	373	|7 days|	none|	none	|yes	|Yes (4 V100/node)|
|test	|5	|48	|Intel "Cascade Lake"|	184	|8 hours|	5	|96 cores|	yes|	No|
|remoteviz	|1|	32	|Intel "Cascade Lake"	|373	|7 days|	none|	none|	no	|Shared V100 GPUs for rendering|
|serial_requeue|	varies|	varies|	Intel|	varies|	7 days	|none	|none	|No|	Yes|
|PI/Lab nodes|	varies|	varies	|varies|	varies|	none|	none|	none|	varies|	varies|


