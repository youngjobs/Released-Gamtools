# Released-Gamtools
# OUTPUT Report of ACC_Mutect2
#####   We have Accelarate Mutect2 of GATK4 (G4M2). The test data is  50X WGS Case and 50X WGS Tumor Data. Accelerate Performance and Accuracy has been tested.
## Release Version


## Usage
     1.--max-job-queue-length 最大内存，默认4096，最小可为256（16G）；
     2—num-threads IPC上可以不设，任务节点上建议设为线程的一半，与-native-pair-hmm-threads大小一致
     3.--native-pair-hmm-threads  IPC上可以不设，任务节点上建议设为线程的一半，与-num-threads大小一致

## Accelerate Performance
##### Compare the total run time between ACC_G4M2 with original G4M2,and the Split Chromosome one.Both Downsample and None Downsample are compared.
<table border="3"  width="770"  cellpadding="2" cellspacing="0" >
  <tr>
      <td  colspan="6" style='height:40pt;' ><b><center>G4M2 Accelerate Performance </center></b></td>
  </tr>
   <tr>
      <td >Data</td>
      <td width="200">Method</td>
      <td width="210">Paraeters</td>
      <td>Downsampled</td>
      <td>Time(h)</td>
      <td>MEM(G)</td>
   </tr>
   <tr>
      <td  rowspan="10">Case 50X WGS Control 50X WGS</td>
      <td>GATK4</td>
      <td>--native-pair-hmm-threads 48</td>
      <td>No</td>
      <td>40.76</td>
      <td>32.1</td>
   </tr>
   <tr>
      <td>GATK4</td>
      <td>--native-pair-hmm-threads 48</td>
      <td>Yes</td>
      <td>33.48</td>
      <td>38.0</td>
   </tr>
   <tr>
      <td>GATK4 Split Chromosome</td>
      <td>split_chromosome*10process</td>
      <td>No</td>
      <td>7.56</td>
      <td> / </td>
   </tr>
   <tr>
      <td>GATK4 Split Chromosome</td>
      <td>split_chromosome*10process</td>
      <td >Yes</td>
      <td>6.7</td>
      <td> / </td>
   </tr>
   <tr>
      <td  rowspan="3">ACC_G4M2</td>
      <td>--native-pair-hmm-threads 24</td>
      <td rowspan="3">Yes</td>
      <td rowspan="3">2.94</td>
      <td rowspan="3">33.1</td>
   </tr>
   <tr>
      <td>--num-threads 24</td>
   </tr>
   <tr>
      <td>--max-job-queue-length 4096</td>
   </tr>
   <tr>
      <td  rowspan="3">ACC_G4M2</td>
      <td>--native-pair-hmm-threads 24</td>
      <td rowspan="3">No</td>
      <td rowspan="3">3.54</td>
      <td rowspan="3">33.1</td>
   </tr>
   <tr>
       <td>--num-threads 24</td>
  </tr>
  <tr>
      <td>--max-job-queue-length 4096</td>
   </tr>
  </div>
 </table>

