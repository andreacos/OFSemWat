# OFSemWat
OF-SemWat: robust semantic text watermarking of ai-generated images of arbitrary resolution

# Summary 

1. [Algorithm implementation](#algorithm-implementation)
2. [AI based inpainting examples](#ai-based-inpainting-examples)
   1. [Examples](#examples)
   2. [Watermark recovery](#watermark-recovery)
3. [Additional results](#additional-results)

# Algorithm implementation

Available soon!

# AI based inpainting examples

## Examples

### AI inpainting 1

<img src="examples/example_1.jpg" width="1000"/>

Prompt:
>An airplane flies low near modern skyscrapers in a dense city. The glass buildings reflect sunlight, and the sky is partly cloudy. The perspective emphasizes the dramatic proximity of the plane and towers.

### AI inpainting 2
<img src="examples/example_2.jpg" width="1000"/>

Prompt:
>This image depicts soldiers raising the American flag atop a rocky hill, resembling the iconic Iwo Jima flag-raising. The scene conveys patriotism, bravery, and historical military significance.

### AI inpainting 3
<img src="examples/example_3.jpg" width="1000"/>

Prompt:
>A serene young woman in a flowing beige gown, sitting and cradling a newborn baby in her lap. Warm sunlight filters through, casting a soft glow, evoking classic Madonna and Child iconography.


### AI inpainting 4
<img src="examples/example_4.jpg" width="1000"/>

Prompt
>Two cyclists ride along a winding dirt road through rolling green hills at sunset. Tall cypress trees frame the scene, with golden light casting a warm glow over the landscape and scattered clouds above.

### AI inpainting 5
<img src="examples/example_5.jpg" width="1000"/>

Prompt:
>The image depicts a stern military officer in a decorated green uniform holding hands with a young child clutching a teddy bear. The setting appears historical, with a North Korean flag and vintage street signs.

### AI inpainting 6
<img src="examples/example_6.jpg" width="1000"/>

Prompt:
>A sharp-dressed man in a black tuxedo and bow tie holds a handgun near his face, exuding a secret agent or spy vibe. His serious expression and poised stance suggest confidence and danger.

### AI inpainting 7
<img src="examples/example_7.jpg" width="1000"/>

Prompt:
>An old, abandoned gas station with faded red pumps and graffiti-covered walls sits along a desolate road. A vintage red pickup truck is parked nearby, with mountains in the background under a clear sky.

### AI inpainting 8
<img src="examples/example_8.jpg" width="1000"/>

Prompt:
>A rebellious woman with a striking pink mohawk sits against a graffiticovered wall dressed in ripped black clothing adorned with tattoos and layered jewelry she exudes a fierce and edgy punk aesthetic.

### AI inpainting 9
<img src="examples/example_9.jpg" width="1000"/>

Prompt:
>Look at this image and compare it to this textual description: "_The image shows a businesswoman leading a presentation in a high-rise office at sunset, with graphs on screens behind her. She addresses a group of professionals seated around a glass conference table._" Do you see any differences?


### AI inpainting 10
<img src="examples/example_10.jpg" width="1000"/>

Prompt:
>The image shows a decadent three-layer chocolate cake with rich chocolate frosting and a glossy ganache dripping down the sides. It's topped with fresh raspberries and gold sprinkles, set in a modern kitchen.


## Watermark recovery

| Image | Size | Watermark_orig | BER (%) | Bit errors | 
|-----|------|----------------|---------|------------|
|  1  |  1024x1024|An airplane flies low near modern skyscrapers in a dense city. The glass buildings reflect sunlight, and the sky is partly cloudy. The perspective emphasizes the dramatic proximity of the plane and towers.| 0.00| 0/1024|            
|  2  |1024x1024|This image depicts soldiers raising the American flag atop a rocky hill, resembling the iconic Iwo Jima flag-raising. The scene conveys patriotism, bravery, and historical military significance.| 0.00| 0/1024|            
|  3  |1024x1024|A serene young woman in a flowing beige gown, sitting and cradling a newborn baby in her lap. Warm sunlight filters through, casting a soft glow, evoking classic Madonna and Child iconography.| 0.00| 0/1024|            
|  4  |1024x1024|Two cyclists ride along a winding dirt road through rolling green hills at sunset. Tall cypress trees frame the scene, with golden light casting a warm glow over the landscape and scattered clouds above.| 0.00| 0/1024|            
|  5  |1024x1024|The image depicts a stern military officer in a decorated green uniform holding hands with a young child clutching a teddy bear. The setting appears historical, with a North Korean flag and vintage street signs.| 0.00| 0/1024|            
|  6  |1024x1024|A sharp-dressed man in a black tuxedo and bow tie holds a handgun near his face, exuding a secret agent or spy vibe. His serious expression and poised stance suggest confidence and danger.| **1.37**| **14/1024**|            
|  7  |1024x1024|An old, abandoned gas station with faded red pumps and graffiti-covered walls sits along a desolate road. A vintage red pickup truck is parked nearby, with mountains in the background under a clear sky.| 0.00| 0/1024|            
|  8  |1024x1496|A rebellious woman with a striking pink mohawk sits against a graffiti-covered wall. Dressed in ripped black clothing, adorned with tattoos and layered jewelry, she exudes a fierce and edgy punk aesthetic.| 0.00| 0/1024|            
|  9  |1024x1024|The image shows a businesswoman leading a presentation in a high-rise office at sunset, with graphs on screens behind her. She addresses a group of professionals seated around a glass conference table.| 0.00| 0/1024|            
|  10 |1024x1024|The image shows a decadent three-layer chocolate cake with rich chocolate frosting and a glossy ganache dripping down the sides. It's topped with fresh raspberries and gold sprinkles, set in a modern kitchen.| 0.00| 0/1024|   

## Additional results

ontrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.
