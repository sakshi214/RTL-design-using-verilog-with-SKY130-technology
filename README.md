# RTL-design-using-verilog-with-SKY130-technology

![Verilog-flyer](https://user-images.githubusercontent.com/69634738/123540568-4be28980-d75d-11eb-83cb-83318934faa3.png)




# DAY-2
# Timing libs hierarchical vs flat synthesis and efficient flop coding styles

## Introduction to timing libraries

.lib is a collection of standard cells containing slow as well as fast cells.
This is how the library starts, it suggests about the operating conditions i.e, voltage, process, temperature.

![image](https://user-images.githubusercontent.com/69634738/123542877-818d6f80-d769-11eb-9af3-f105a8d710fe.png)

The cell contains the information about leakage power,area,delay,input capacitance, timing etc.

![image](https://user-images.githubusercontent.com/69634738/123543028-56575000-d76a-11eb-84fb-508a7ee70c1b.png)

![image](https://user-images.githubusercontent.com/69634738/123543258-37a58900-d76b-11eb-8926-a249b769dae1.png)
![image](https://user-images.githubusercontent.com/69634738/123543449-1ee9a300-d76c-11eb-9634-59da825572db.png)


## Heirarchical vs Flat Synthesis
This is to show how the netlist looks around in heirarchical synthesis and flat synthesis

The file is multiple modules containing two sub modules with AND and OR gates. The module named multiple module is instantiating the sub modules. 


![image](https://user-images.githubusercontent.com/69634738/123591394-87d32880-d809-11eb-8c96-8d7708b9d91f.png)

![image](https://user-images.githubusercontent.com/69634738/123592880-768b1b80-d80b-11eb-885a-a4df66e2e638.png)
This is the information about the submodules.

![image](https://user-images.githubusercontent.com/69634738/123593110-c538b580-d80b-11eb-97dc-ffb42b35cb43.png)

![image](https://user-images.githubusercontent.com/69634738/123593231-e6010b00-d80b-11eb-84a5-e5e4d05e4d16.png)
It is not showing AND and OR directly but instead U1 AND U2. This is the heirarchical design.

![image](https://user-images.githubusercontent.com/69634738/123593328-00d37f80-d80c-11eb-8313-83da8dd471d1.png)
Now to see how the netlist looks like
![image](https://user-images.githubusercontent.com/69634738/123594135-f9f93c80-d80c-11eb-87ea-f6cc750f8e55.png)

Use of flatten: flatten is a command to write flat netlist.
![image](https://user-images.githubusercontent.com/69634738/123595031-0c27aa80-d80e-11eb-801f-7041ccd6ac30.png)
There are no heirarchies, its a single netlist.

![image](https://user-images.githubusercontent.com/69634738/123595129-26fa1f00-d80e-11eb-8da7-dcbe57668662.png)
There is no U1 and U2 now AND and OR gates are shown.

![image](https://user-images.githubusercontent.com/69634738/123595198-41cc9380-d80e-11eb-865b-9b34291b8bb8.png)












