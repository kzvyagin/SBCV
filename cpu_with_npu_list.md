<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/kzvyagin/SBCV"> Single-board computer vision</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/kzvyagin">Konstantin Zvyagin</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"> <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a></p>


<style type="text/css">
.tg  {border-collapse:collapse;border-color:#bbb;border-spacing:0;}
.tg td{background-color:#E0FFEB;border-color:#bbb;border-style:solid;border-width:1px;color:#594F4F;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#9DE0AD;border-color:#bbb;border-style:solid;border-width:1px;color:#493F3F;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:center;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">CPU NAME</th>
    <th class="tg-0pky">CPU cores</th>
    <th class="tg-0pky">NPU TFLPOS </th>
    <th class="tg-0pky">NPU github / SDK </th>
    <th class="tg-0pky">Boards / Articles</th>
  </tr>
</thead>

<tbody>
 <tr>
    <td class="tg-0pky" colspan="5"> <b>RockChip family</b></td>
  </tr>
  <tr>
    <td class="tg-0pky">RK3588/RK3588s </td>
    <td class="tg-0pky">Quad core Cortex-A76 <br>and<br> Quad core Cortex-A55 <br> configuration DynamIQ </td>
    <td class="tg-0pky">4</td>
    <td class="tg-0pky"><a href="https://github.com/rockchip-linux/rknpu2"> rknpu2 Github</a>   </td>
    <td class="tg-0pky"> <a href="http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-5.html">OrangePI 5</a> </td>
  </tr>
  <tr>
    <td class="tg-0pky"> RK3566/RK3568</td>
    <td class="tg-0pky"> Quad-core Arm Cortex-A55 processor @ 1.6 GHz </td>
    <td class="tg-0pky">0.8</td>
    <td class="tg-0pky"><a href="https://github.com/rockchip-linux/rknpu2"> rknpu2 Github</a>    </td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">RV1103/RV1106</td>
    <td class="tg-0pky">Cortex A7@1.2GHz + RISC-V</td>
    <td class="tg-0pky">0.5  </td>
    <td class="tg-0pky"><a href="https://github.com/rockchip-linux/rknpu2"> rknpu2 Github</a> </td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">RK3562</td>
    <td class="tg-0pky">4 x Cortex-A53 2000 МГц</td>
    <td class="tg-0pky">1</td>
    <td class="tg-0pky"><a href="https://github.com/rockchip-linux/rknpu2"> rknpu2 Github</td>
    <td class="tg-0pky"></td>
  </tr>
   <tr>
    <td class="tg-0pky" colspan="5"> <b>Amlogic family</b></td>
  </tr>

  <tr>
    <td class="tg-0pky">Amlogic A311D</td>
    <td class="tg-0pky">Quad core ARM Cortex-A73 and dual core ARM Cortex-A53 CPU</td>
    <td class="tg-0pky">5</td>
    <td class="tg-0pky"><a href="https://github.com/opencv/opencv/wiki/TIM-VX-Backend-For-Running-OpenCV-On-NPU">OpenCV-On-NPU Github </a>   <br> <a href="https://forum.khadas.com/t/npu-documentation-and-tools/5214">Khadas npu doc</a>   </td>
    <td class="tg-0pky"> <a href="https://www.khadas.com/vim3">Khadas vim3</a> <br> <a href="Banana Pi BPI-M2S SoC Amlogic A311D и S922X">Banana Pi BPI-M2S</a>    </td>
  </tr>
  <tr>
    <td class="tg-0pky">Amlogic S905D3</td>
    <td class="tg-0pky">Quad-core Cortex-A53</td>
    <td class="tg-0pky">1.2 </td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"> Khadas VIM3L</td>
  </tr>
    <tr>
    <td class="tg-0pky"> Amlogic S922D</td>
    <td class="tg-0pky"> Quad-core ARM Cortex-A73+Dual-Core ARM Cortex-A53-based SoC </td>
    <td class="tg-0pky">5</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">Khadas</td>
  </tr>

  <tr>
    <td class="tg-0pky" colspan="5"> <b>Synaptic family</b></td>
  </tr>
  <tr>
    <td class="tg-0pky">VS680</td>
    <td class="tg-0pky">Quad-core Arm Cortex-A73 </td>
    <td class="tg-0pky"> 7.9 </td>
    <td class="tg-0pky"><a href="https://wiki.banana-pi.org/Banana_Pi_BPI-M6">Wiki Banana PI</a>       </td>
    <td class="tg-0pky"></td>
  </tr>
 <tr>
    <td class="tg-0pky" colspan="5"> <b>PCI-E Acceleration Modules </b></td>
  </tr>
  <tr>
    <td class="tg-0pky">Hailo-8 AI Accelerator</td>
    <td class="tg-0pky">-----</td>
    <td class="tg-0pky">26</td>
    <td class="tg-0pky"> <a href="https://github.com/hailo-ai">Github Hailo AI</a>       </td>
    <td class="tg-0pky"> <a href="https://hailo.ai/products/ai-accelerators/hailo-8-m2-ai-acceleration-module/#hailo8-m2-overview">Hailo AI official site</a> </td>
  </tr>

   <tr>
    <td class="tg-0pky" colspan="5"> <b>MediaTek</b></td>
  </tr>
  <tr>
    <td class="tg-0pky">MediaTek Genio 1200</td>
    <td class="tg-0pky"> Octa-core processor with four Cortex-A78 cores @ up to 2.2 GHz, four Cortex-A55 cores</td>
    <td class="tg-0pky"> 4.8 </td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
    <tr>
    <td class="tg-0pky" colspan="5"> <b>Sophgo family</b></td>
  </tr>
  <tr>
    <td class="tg-0pky">Sophgo SG2380</td>
    <td class="tg-0pky"> 16-core SiFive P670 (RV64GCVH) с 64-bit RISC-V @ up to 2,5 ГГц с RISC-V Vector v1.0, Vector Crypto  </td>
    <td class="tg-0pky">20</td>
    <td class="tg-0pky"><a href="https://github.com/sophgo"> Github sophgo</a> </td>
    <td class="tg-0pky"><a href="https://cnx-software.ru/2023/10/22/sophgo-sg2380-16-yadernyj-proczessor-sifive-p670-risc-v-s-taktovoj-chastotoj-25-ggcz-i-ai-uskoritelem-20-tops/">sophgo-sg2380-16</a> </td>
  </tr>
  <tr>
    <td class="tg-0pky">SOPHGO SOPHON BM1684X Cortex-A53 AI SoC </td>
    <td class="tg-0pky"> Octa core Arm Cortex-A53  up to  2,3 GHz  </td>
    <td class="tg-0pky">up to  32TOPS (INT8) , 16 TFLOPS (FP16/BF16), 2 TFLOPS (FP32) </td>
    <td class="tg-0pky"> <a href="https://github.com/sophgo"> Github sophgo</a> <br> <a href=https://sophon.ai/product/introduce/bm1684x.html>bm1684x</a>         </td>
    <td class="tg-0pky"><a href="https://aliexpress.ru/item/1005005955504919.html?sku_id=12000035015414681&spm=a2g2w.productlist.search_results.4.31536071YU6y4O">Firefly Core-1684XJD4</a> <br>  <a href="https://cnx-software.ru/2023/04/02/kompyuter-sophon-bm1684-bm1684x-edge-ai-obespechivaet-do-32-tops-dekodiruet-do-32-video-full-hd-odnovremenno/">Kompyuter-sophon-bm1684</a></td>
  </tr>
  <tr>
    <td class="tg-0pky">SOPHGO SOPHON BM1684 Cortex-A53 AI SoC</td>
    <td class="tg-0pky">Octa core Arm Cortex-A53  up to  2,3 GHz </td>
    <td class="tg-0pky"> 17,6 TOPS (INT8) , 2,2 TOPS (FP32)     </td>
    <td class="tg-0pky"><a href="https://github.com/sophgo"> Github sophgo</a> <br>  <a href="https://sophon.ai/product/introduce/bm1684.html">bm1684</a>        </td>
    <td class="tg-0pky"><a href="https://aliexpress.ru/item/1005004821362248.html?sku_id=12000030614939176&spm=a2g2w.productlist.search_results.0.5be53318HGl7zh">Core-1684JD4 BM1684 firefly</a>   <br> <a href="https://aliexpress.ru/item/1005004827576682.html?sku_id=12000030636750157&spm=a2g2w.productlist.search_results.4.5be53318HGl7zh">EVM1684 development board</a> </td>
  </tr>
  <tr>
    <td class="tg-0pky">SOPHGO SG2000/SG2002</td>
    <td class="tg-0pky"> 1 GHz C906 RISC-V or 1 GHz ARM Cortex-A53 AND 700 MHz C906 RISC-V core </td>
    <td class="tg-0pky"> 0.5 TOPS(INT8)  <br> or <br>  1 TOPS(INT8)  </td>
    <td class="tg-0pky"><a href="https://github.com/sipeed/LicheeRV-Nano-Build/tree/v4.1.0-licheervnano">LicheeRV GitHub</a></td>
    <td class="tg-0pky"> <a href="https://habr.com/ru/companies/ru_mts/articles/793880/">Habr article</a> <br> <a href="https://milkv.io/chips/sg2000">Milkv sg2000</a> <br><a href="https://milkv.io/chips/sg2002">Milkv sg2002</a> </td>
  <tr>
    <td class="tg-0pky" colspan="5"> <b>Allwinner family</b></td>
  </tr>
  </tr>
    <tr>
    <td class="tg-0pky"> Allwinner T527 </td>
    <td class="tg-0pky">Octa-Core Cortex A55   <br>   RISC-V@200MHz </td>
    <td class="tg-0pky">2Tops </td>
    <td class="tg-0pky"> <a href="https://github.com/YuzukiHD/SyterKit" >SyterKit Github </a>     </td>
    <td class="tg-0pky"><a href="https://cnx-software.ru/2024/03/09/sistema-na-module-allwinner-t527-osnashhena-vosmiyadernym-proczessorom-cortex-a55-i-uskoritelem-iskusstvennogo-intellekta-2-tops/">Board</a> </td>
  </tr>
        <tr>
    <td class="tg-0pky">Allwinner V831</td>
    <td class="tg-0pky">1GHz Cortex-A7</td>
    <td class="tg-0pky">0.23</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"><a href="https://wiki.sipeed.com/hardware/en/maixII/M2/resources.html"> MaixII dock</a> <a href="https://linuxgizmos.com/cam-equipped-dev-kit-runs-linux-on-npu-enabled-allwinner-v831/">MaxII dev-kit</a></td>
  </tr>

<tr>
    <td class="tg-0pky">Allwinner V851S/V851SE</td>
    <td class="tg-0pky">one Arm Cortex-A7 900 Mhz <br>and<br>
        one RISC-V  600 Mhz</td>
    <td class="tg-0pky">0,5 TOPS</td>
    <td class="tg-0pky"> <a href="https://cnx-software.ru/2022/10/07/allwinner-v851s-v851se-nedorogaya-odnokristalnaya-sistema-dlya-kamer-vklyuchayushhaya-64-mb-ddr2-05-tops-npu/">CNX cpu review</a> <br> <a href="https://github.com/YuzukiHD/Yuzukilizard"> Dev board GitHub </a></td>
    <td class="tg-0pky"><a href="https://cnx-software.ru/2022/09/19/yuzuki-chameleon-odnoplatnyj-kompyuter-povtoryayushhij-formu-raspberry-pi-model-a-osnashhennyj-proczessorom-allwinner-h616/">CNX development board review</a></td>
  </tr>
    <tr>
    <td class="tg-0pky">Allwinner V853/V853s</td>
    <td class="tg-0pky">Arm Cortex-A7 1 GHz <br>Alibaba Xuantie E907 RISC-V</td>
    <td class="tg-0pky"> 1/0.8 TOPS</td>
    <td class="tg-0pky"><a href="https://cnx-software.ru/2022/05/07/proczessor-allwinner-v853-arm-cortex-a7-risc-v-postavlyaetsya-s-1-npu-tops-dlya-prilozhenij-ai-vision/">CNX cpu review</a><br><a href="https://github.com/YuzukiHD/ProjectYosemite">Dev board GitHub</a></td>
    <td class="tg-0pky"></td>
  </tr>
    <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
    <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
 <tr>
    <td class="tg-0pky" colspan="5"> <b>Texas Instruments</b></td>
  </tr>
        <tr>
    <td class="tg-0pky">AM62A3 <br> AM62A3-Q1 <br> AM62A7 <br> AM62A7-Q1</td>
    <td class="tg-0pky"> Quad-core Cortex-A53</td>
    <td class="tg-0pky">1TOPS </td>
    <td class="tg-0pky"><a href="https://www.cnx-software.com/2023/03/20/texas-instruments-am62a-am68a-am69a-arm-cortex-vision-processors-devkits/">CNX review</a></td>
    <td class="tg-0pky"></td>
  </tr>
          <tr>
    <td class="tg-0pky">AM68A</td>
    <td class="tg-0pky">Dual-core Cortex-A72</td>
    <td class="tg-0pky">8 TOPS </td>
    <td class="tg-0pky"><a href="https://www.cnx-software.com/2023/03/20/texas-instruments-am62a-am68a-am69a-arm-cortex-vision-processors-devkits/">CNX review</a></td>
    <td class="tg-0pky"></td>
  </tr>
          <tr>
    <td class="tg-0pky">AM69A</td>
    <td class="tg-0pky">Octa-core Cortex-A72 SoC</td>
    <td class="tg-0pky">32 TOPS </td>
    <td class="tg-0pky"><a href="https://www.cnx-software.com/2023/03/20/texas-instruments-am62a-am68a-am69a-arm-cortex-vision-processors-devkits/">CNX review</a></td>
    <td class="tg-0pky"></td>
  </tr>
  
  <tr>
    <td class="tg-0pky" colspan="5"> <b>Other</b></td>
  </tr>
  <tr>
    <td class="tg-0pky">AXERA AX620A 4K AI SoC</td>
    <td class="tg-0pky">4 * Cortex-A7</td>
    <td class="tg-0pky">14 (INT4) <br> 3.2 (INT8) </td>
    <td class="tg-0pky"><a  href="https://wiki.sipeed.com/hardware/en/maixIII/ax-pi/dev_prepare.html">wiki</a>  </td>
    <td class="tg-0pky">MAIX-III AXera-Pi <br> Sipeed M3AXPI <br> <a href=https://cnx-software.ru/2022/11/09/axera-ax620a-4k-ai-soc-obespechivaet-do-144-tops-dlya-prilozhenij-kompyuternogo-zreniya>axera-ax620a-4k</a>   </td>
  </tr>
  <tr>
    <td class="tg-0pky">RZ/V2H</td>
    <td class="tg-0pky">4 x Arm Cortex-A55  1.8 GHz <br> 2 x Arm Cortex-R8 MCU 800 MHz <br> 1 x Arm Cortex-M33 MCU 200 MHz <br>    </td>
    <td class="tg-0pky">DRP-AI3 до 8 TOPS</td>
    <td class="tg-0pky"><a href="https://github.com/renesas-rz/rzv_ai_sdk">Rzv ai Sdk</a>   </td>
    <td class="tg-0pky"><a href="https://cnx-software.ru/2024/03/07/kaki-pi-eto-renesas-rz-v2h-ai-sbc-v-stile-raspberry-pi-s-chetyrmya-razemami-dlya-kamer-i-interfejsom-pcie-3-0/">Kaki pi cnx link</a>   <br> <br> <a href="https://www.kaki-pi.ai/">Kaki pi Ai<a>  </td>
  </tr>
    <tr>
    <td class="tg-0pky">RTS3916N</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">1Tops  </td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
      <tr>
    <td class="tg-0pky">Kendryte K210</td>
    <td class="tg-0pky">400MHz Kendryte K210 RISC-V </td>
    <td class="tg-0pky">1TOPS AI </td>
    <td class="tg-0pky"><a href="https://github.com/kendryte">Kendryte GitHub</a></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">  Ethos-U55</td>
    <td class="tg-0pky"> Dual Cortex-M55 </td>
    <td class="tg-0pky">0.5 Tops</td>
    <td class="tg-0pky"><a href="https://www.arm.com/products/silicon-ip-cpu/ethos/ethos-u55">Offical documntation</a> <br> <a href="https://github.com/zephyrproject-rtos/hal_ethos_u">Zephyr AI driver</a> <a href="https://github.com/nxp-imx/ethos-u-vela">Model compiler tool</a></td>
    <td class="tg-0pky"></td>
  </tr>
        <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>

</tbody>
</table>






