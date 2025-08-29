# OFSemWat

This repository contains additional information / material for the paper:

**_OF-SemWat: ROBUST SEMANTIC TEXT WATERMARKING OF AI-GENERATED IMAGES OF ARBITRARY RESOLUTION_**

Benedetta Tondi, Andrea Costanzo, Mauro Barni


# Summary 

1. [Algorithm implementation](#algorithm-implementation)
2. [AI based inpainting examples](#ai-based-inpainting-examples)
   1. [Examples](#examples)
   2. [Watermark recovery](#watermark-recovery)
3. [Watermark recovery via LLM](#watermark-recovery-via-llm)

# Algorithm implementation

An implementation of the watermarking algorithm and the scripts to replicate the results with be released upon publication of the paper.

```
Code and tools available soon
```


# AI based inpainting examples

## Examples

For each image, from left to right, we show:
- The input, to-be-watermarked image
- The watermarked image. The embedded watermark is a brief description of the image itself (200 characters) encoded to a binary sequence of 1000 bits. Below each sequence of figures we report the textual version of the watermark.
- The watermarked, edited image. Specifically, the image was semantically modified using prompt-based AI inpainting within [Freepik's AI suite](https://www.freepik.com/pikaso/image-editor).
- A binary mask highlighting the modified region. The mask is the binarised difference between watermarked and edited image, without further morphological operators, just for the sake of visualization. Above the mask, we report the percentage of modified pixels.

The BER(%) for all te images following the AI-inpainting is 0 for all the images except image 6 (BER 1.4%). See below for more details.

### AI inpainting 1

<img src="examples/example_1.jpg" width="1000"/>

Embedded watermark:
>An airplane flies low near modern skyscrapers in a dense city. The glass buildings reflect sunlight, and the sky is partly cloudy. The perspective emphasizes the dramatic proximity of the plane and towers.

### AI inpainting 2
<img src="examples/example_2.jpg" width="1000"/>

Embedded watermark:
>This image depicts soldiers raising the American flag atop a rocky hill, resembling the iconic Iwo Jima flag-raising. The scene conveys patriotism, bravery, and historical military significance.

### AI inpainting 3
<img src="examples/example_3.jpg" width="1000"/>

Embedded watermark:
>A serene young woman in a flowing beige gown, sitting and cradling a newborn baby in her lap. Warm sunlight filters through, casting a soft glow, evoking classic Madonna and Child iconography.


### AI inpainting 4
<img src="examples/example_4.jpg" width="1000"/>

Prompt
>Two cyclists ride along a winding dirt road through rolling green hills at sunset. Tall cypress trees frame the scene, with golden light casting a warm glow over the landscape and scattered clouds above.

### AI inpainting 5
<img src="examples/example_5.jpg" width="1000"/>

Embedded watermark:
>The image depicts a stern military officer in a decorated green uniform holding hands with a young child clutching a teddy bear. The setting appears historical, with a North Korean flag and vintage street signs.

### AI inpainting 6
<img src="examples/example_6.jpg" width="1000"/>

Embedded watermark:
>A sharp-dressed man in a black tuxedo and bow tie holds a handgun near his face, exuding a secret agent or spy vibe. His serious expression and poised stance suggest confidence and danger.

### AI inpainting 7
<img src="examples/example_7.jpg" width="1000"/>

Embedded watermark:
>An old, abandoned gas station with faded red pumps and graffiti-covered walls sits along a desolate road. A vintage red pickup truck is parked nearby, with mountains in the background under a clear sky.

### AI inpainting 8
<img src="examples/example_8.jpg" width="1000"/>

Embedded watermark:
>A rebellious woman with a striking pink mohawk sits against a graffiticovered wall dressed in ripped black clothing adorned with tattoos and layered jewelry she exudes a fierce and edgy punk aesthetic.

### AI inpainting 9
<img src="examples/example_9.jpg" width="1000"/>

Embedded watermark:
>The image shows a businesswoman leading a presentation in a high-rise office at sunset, with graphs on screens behind her. She addresses a group of professionals seated around a glass conference table.


### AI inpainting 10
<img src="examples/example_10.jpg" width="1000"/>

Embedded watermark:
>The image shows a decadent three-layer chocolate cake with rich chocolate frosting and a glossy ganache dripping down the sides. It's topped with fresh raspberries and gold sprinkles, set in a modern kitchen.


## Watermark recovery

Here we report BER(%) following watermark recovery in the AI-inpainted, watermarked images.

| Image | Size | Watermark_orig | BER (%) | Bit errors | 
|-----|------|----------------|---------|------------|
|  1  |  1024x1024|An airplane flies low near modern skyscrapers in a dense city. The glass buildings reflect sunlight, and the sky is partly cloudy. The perspective emphasizes the dramatic proximity of the plane and towers.| 0.00| 0/1000|            
|  2  |1024x1024|This image depicts soldiers raising the American flag atop a rocky hill, resembling the iconic Iwo Jima flag-raising. The scene conveys patriotism, bravery, and historical military significance.| 0.00| 0/1000|            
|  3  |1024x1024|A serene young woman in a flowing beige gown, sitting and cradling a newborn baby in her lap. Warm sunlight filters through, casting a soft glow, evoking classic Madonna and Child iconography.| 0.00| 0/1000|            
|  4  |1024x1024|Two cyclists ride along a winding dirt road through rolling green hills at sunset. Tall cypress trees frame the scene, with golden light casting a warm glow over the landscape and scattered clouds above.| 0.00| 0/1000|            
|  5  |1024x1024|The image depicts a stern military officer in a decorated green uniform holding hands with a young child clutching a teddy bear. The setting appears historical, with a North Korean flag and vintage street signs.| 0.00| 0/1000|            
|  6  |1024x1024|A sharp-dressed man in a black tuxedo and bow tie holds a handgun near his face, exuding a secret agent or spy vibe. His serious expression and poised stance suggest confidence and danger.| **1.40**| **14/1000**|            
|  7  |1024x1024|An old, abandoned gas station with faded red pumps and graffiti-covered walls sits along a desolate road. A vintage red pickup truck is parked nearby, with mountains in the background under a clear sky.| 0.00| 0/1000|            
|  8  |1024x1496|A rebellious woman with a striking pink mohawk sits against a graffiti-covered wall. Dressed in ripped black clothing, adorned with tattoos and layered jewelry, she exudes a fierce and edgy punk aesthetic.| 0.00| 0/1000|            
|  9  |1024x1024|The image shows a businesswoman leading a presentation in a high-rise office at sunset, with graphs on screens behind her. She addresses a group of professionals seated around a glass conference table.| 0.00| 0/1000|            
|  10 |1024x1024|The image shows a decadent three-layer chocolate cake with rich chocolate frosting and a glossy ganache dripping down the sides. It's topped with fresh raspberries and gold sprinkles, set in a modern kitchen.| 0.00| 0/1000|   

## Watermark recovery via LLM

- **Image**: Image index according to the previous Section 
- **Processing**: The image processing that was applied to the image
- **Parameter**: The parameter of the processing (e.g. Quality Factor for JPEG, resizing factor for up/down scaling, angle for rotation etc.)
- **BER**: Watermark recovery BER(%) **following processing**
- **Sim_orig_rec**: [all-MiniLM-L6-2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) similarity between the originally embedded watermark and the recovered watermark prior to ChatGPT reconstruction
- **Sim_orig_gpt**: [all-MiniLM-L6-2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) similarity between the originally embedded watermark and ChatGPT reconstructon
- **Delta_sim**: the similarity variation between *Sim_orig_rec* and *Sim_orig_gpt*

| Image | Processing | Parameter | BER(%) | Sim_orig_gpt | Sim_orig_rec | Delta_sim |
|-------|------------|-----------|--------|--------------|--------------|-----------|
| 8     | ROTATE     | 5.0       | 23     | 0.054        | 0.0060       | 0.048     |
| 7     | ROTATE     | -10.0     | 22     | 0.370        | 0.1559       | 0.214     |
| 5     | JPEG       | 30.0      | 21     | 0.244        | 0.3386       | -0.095    |
| 7     | RESIZE     | 1.7       | 19     | 0.347        | 0.2233       | 0.123     |
| 5     | ROTATE     | 20.0      | 19     | 0.310        | 0.2718       | 0.038     |
| 4     | CROP       | 35.0      | 19     | 0.129        | 0.2618       | -0.132    |
| 5     | RESIZE     | 1.2       | 18     | 0.692        | 0.2015       | 0.490     |
| 8     | ROTATE     | -5.0      | 18     | 0.534        | 0.2925       | 0.242     |
| 2     | CROP       | 20.0      | 18     | 0.370        | 0.2318       | 0.139     |
| 6     | RESIZE     | 1.5       | 18     | 0.010        | 0.3026       | -0.293    |
| 6     | RESIZE     | 1.1       | 18     | 0.092        | 0.0753       | 0.017     |
| 6     | JPEG       | 80.0      | 18     | 0.074        | 0.2038       | -0.130    |
| 5     | ROTATE     | -20.0     | 17     | 0.399        | 0.3371       | 0.061     |
| 8     | CROP       | 20.0      | 17     | 0.021        | 0.2058       | -0.184    |
| 8     | JPEG       | 40.0      | 16     | 0.472        | 0.2088       | 0.263     |
| 6     | RESIZE     | 1.7       | 16     | 0.033        | 0.2242       | -0.192    |
| 2     | JPEG       | 30.0      | 15     | 0.800        | 0.2649       | 0.535     |
| 9     | ROTATE     | 5.0       | 15     | 0.647        | 0.2843       | 0.363     |
| 9     | ROTATE     | -10.0     | 15     | 0.500        | 0.1512       | 0.349     |
| 5     | RESIZE     | 1.7       | 15     | 0.578        | 0.1891       | 0.389     |
| 9     | ROTATE     | 10.0      | 15     | 0.442        | 0.3739       | 0.068     |
| 3     | JPEG       | 20.0      | 15     | 0.536        | 0.2620       | 0.274     |
| 5     | CROP       | 30.0      | 14     | 0.066        | 0.3677       | -0.302    |
| 2     | RESIZE     | 1.5       | 14     | 0.085        | 0.0823       | 0.003     |
| 6     | RESIZE     | 0.9       | 13     | 0.636        | 0.2603       | 0.376     |
| 7     | CROP       | 30.0      | 13     | 0.514        | 0.2224       | 0.292     |
| 2     | RESIZE     | 1.7       | 13     | 0.085        | 0.1258       | -0.040    |
| 9     | ROTATE     | -5.0      | 12     | 0.892        | 0.5364       | 0.355     |
| 8     | RESIZE     | 0.9       | 12     | 0.887        | 0.2524       | 0.635     |
| 5     | ROTATE     | 15.0      | 12     | 0.837        | 0.2746       | 0.562     |
| 3     | CROP       | 35.0      | 12     | 0.839        | 0.4493       | 0.390     |
| 7     | ROTATE     | -5.0      | 11     | 0.756        | 0.4986       | 0.257     |
| 7     | ROTATE     | 5.0       | 11     | 0.737        | 0.2965       | 0.440     |
| 8     | RESIZE     | 0.7       | 10     | 0.912        | 0.3353       | 0.577     |
| 8     | JPEG       | 50.0      | 9      | 0.998        | 0.3853       | 0.613     |
| 9     | JPEG       | 40.0      | 9      | 0.974        | 0.5039       | 0.470     |
| 5     | ROTATE     | -15.0     | 9      | 0.925        | 0.5236       | 0.401     |
| 4     | ROTATE     | 20.0      | 8      | 0.969        | 0.6952       | 0.273     |
| 1     | ROTATE     | -15.0     | 8      | 0.928        | 0.4215       | 0.507     |
| 6     | RESIZE     | 1.2       | 8      | 0.668        | 0.5807       | 0.087     |
| 4     | ROTATE     | -20.0     | 7      | 0.988        | 0.4525       | 0.536     |
| 5     | JPEG       | 40.0      | 7      | 0.992        | 0.4638       | 0.528     |
| 1     | CROP       | 20.0      | 6      | 0.970        | 0.5426       | 0.427     |
| 1     | ROTATE     | 15.0      | 6      | 0.968        | 0.5689       | 0.399     |
| 2     | JPEG       | 40.0      | 6      | 0.891        | 0.7012       | 0.190     |
| 8     | JPEG       | 60.0      | 5      | 0.995        | 0.6522       | 0.343     |
| 6     | JPEG       | 90.0      | 5      | 0.862        | 0.5812       | 0.281     |
| 7     | RESIZE     | 1.5       | 5      | 0.992        | 0.5130       | 0.479     |
| 10    | CROP       | 40.0      | 5      | 0.996        | 0.6765       | 0.320     |
| 6     | RESIZE     | 1.3       | 5      | 0.910        | 0.7356       | 0.175     |
| 4     | CROP       | 30.0      | 5      | 0.968        | 0.6691       | 0.299     |
| 3     | RESIZE     | 1.5       | 5      | 1.000        | 0.8189       | 0.181     |
| 4     | RESIZE     | 1.2       | 4      | 0.999        | 0.6553       | 0.344     |
| 5     | ROTATE     | 10.0      | 4      | 0.999        | 0.7082       | 0.291     |
| 3     | RESIZE     | 1.7       | 4      | 0.972        | 0.7148       | 0.257     |
| 7     | JPEG       | 30.0      | 4      | 0.934        | 0.6884       | 0.246     |
| 2     | JPEG       | 50.0      | 4      | 0.856        | 0.8159       | 0.040     |
| 9     | JPEG       | 50.0      | 3      | 0.974        | 0.8131       | 0.161     |
| 5     | ROTATE     | -10.0     | 3      | 0.982        | 0.7422       | 0.240     |
| 2     | JPEG       | 60.0      | 3      | 0.999        | 0.7745       | 0.224     |
| 9     | CROP       | 20.0      | 3      | 0.998        | 0.8593       | 0.139     |
| 3     | CROP       | 30.0      | 3      | 0.994        | 0.8828       | 0.112     |
| 4     | ROTATE     | -15.0     | 3      | 0.982        | 0.8949       | 0.087     |
| 7     | CROP       | 20.0      | 2      | 0.992        | 0.9295       | 0.063     |
| 1     | ROTATE     | 10.0      | 2      | 1.000        | 0.7358       | 0.264     |
| 2     | RESIZE     | 0.9       | 2      | 0.999        | 0.7567       | 0.242     |
| 9     | RESIZE     | 0.9       | 2      | 0.998        | 0.7778       | 0.220     |
| 8     | CROP       | 10.0      | 2      | 0.997        | 0.8263       | 0.171     |
| 8     | RESIZE     | 0.8       | 2      | 0.997        | 0.8293       | 0.168     |
| 5     | ROTATE     | 5.0       | 2      | 0.999        | 0.8351       | 0.164     |
| 9     | RESIZE     | 0.7       | 2      | 0.992        | 0.8412       | 0.151     |
| 5     | RESIZE     | 1.5       | 2      | 0.999        | 0.8624       | 0.137     |
| 2     | RESIZE     | 0.7       | 2      | 1.000        | 0.9300       | 0.070     |
| 1     | ROTATE     | -10.0     | 2      | 0.829        | 0.9547       | -0.125    |
| 8     | RESIZE     | 1.1       | 2      | 0.963        | 0.9066       | 0.056     |
| 10    | JPEG       | 20.0      | 1      | 0.981        | 0.7271       | 0.253     |
| 3     | ROTATE     | -20.0     | 1      | 0.994        | 0.6602       | 0.333     |
| 8     | JPEG       | 70.0      | 1      | 0.997        | 0.8276       | 0.170     |
| 1     | JPEG       | 20.0      | 1      | 0.999        | 0.8323       | 0.167     |
| 4     | RESIZE     | 1.5       | 1      | 0.999        | 0.8380       | 0.161     |
| 3     | RESIZE     | 1.2       | 1      | 0.995        | 0.8444       | 0.151     |
| 4     | RESIZE     | 1.7       | 1      | 1.000        | 0.8750       | 0.125     |
| 8     | RESIZE     | 1.7       | 1      | 0.998        | 0.8842       | 0.114     |
| 8     | RESIZE     | 1.5       | 1      | 0.997        | 0.8880       | 0.109     |
| 4     | ROTATE     | 15.0      | 1      | 0.999        | 0.8995       | 0.100     |
| 5     | ROTATE     | -5.0      | 1      | 0.999        | 0.9024       | 0.097     |
| 7     | CROP       | 10.0      | 1      | 0.992        | 0.9036       | 0.089     |
| 5     | CROP       | 20.0      | 1      | 0.999        | 0.9012       | 0.098     |
| 6     | JPEG       | 100.0     | 1      | 0.981        | 0.9233       | 0.058     |
| 3     | JPEG       | 30.0      | 1      | 0.999        | 0.9094       | 0.089     |
| 2     | RESIZE     | 0.8       | 1      | 0.999        | 0.9311       | 0.067     |
| 10    | CROP       | 35.0      | 1      | 1.000        | 0.9440       | 0.056     |
| 2     | RESIZE     | 1.1       | 1      | 0.999        | 0.9466       | 0.052     |
| 2     | CROP       | 10.0      | 1      | 0.999        | 0.9554       | 0.043     |
| 7     | RESIZE     | 0.7       | 1      | 0.925        | 0.9591       | -0.034    |


