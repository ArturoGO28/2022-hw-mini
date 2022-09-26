# EC463 Hardware Mini Project

Author: Arturo Garcia Ovalles

Date: 2022-09-25

# Note

I'm a Computer Engineering Student and was originally assigned to the Software Mini Project. However, my teammate joined an interdisciplinary team for the senior design project and told me that he would not complete the SW Mini Project as he was not required to do it anymore. Because I was more interested in the Hardware Mini Project and had not teammate anymore (giving me more flexibility to switch to the Hardware Mini Project without causing problems to someone), I talked to Professor Osama and Professor Hirsch, to switch to the Hardware Mini Project and they accepted.

# Links to videos/Measurements

[Original pwm_led_fade](https://drive.google.com/file/d/1v74u9RG3M5If4X5D9nLIFN0iqOnSByY6/view?usp=sharing)

[Modified pwm_led_fade](https://drive.google.com/file/d/1v-A0Ty6Lvikz6CxTGcLnwk57-stu7fSE/view?usp=sharing)

# Summary of Modification

For this Mini Project assignment, I used the on-board LED of a Raspberry Pi Pico to test different fading/changing LED patterns. The original pwm_led_fade example is a C program that makes the LED fade from zero to maximum brightness, as you can see in the "Original pwm_led_fade" video above. I modified this example by increasing the fading speed of the LED. As you can see in the "Modified pwm_led_fade" video above, the LED fades much more quickly than the original example. I intended this modified version to be more similar to the fading speed that emergency service vehicles use, such as police cars. The program works by creating a PWM interrupt handler that continuously repeats and effectively takes over program control. The function "on_pwm_wrap" is part of the interrupt handler and has the logic for the fading/changing pattern of the on-board led. "fade" is the rate at which the brightness of the led changes, so I increased it from 1 to 5 to make it fade faster. This change accomplished my original intention as it causes the LED to quickly and smoothly fade the brightness of the LED without noticing that the led turns off at any point.