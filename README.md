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

synthsis at submodule 1 level:
![image](https://user-images.githubusercontent.com/69634738/123609784-9c212080-d81d-11eb-9fdb-1388eb5d0063.png)

![image](https://user-images.githubusercontent.com/69634738/123609925-bd820c80-d81d-11eb-98de-4340a8be05e0.png)

When is it needed to do module level synthesis?
i When we have multiple instances of same module
ii In massive designs DIVIDE AND CONQUER approach is used.

To control which module is to be synthesised the keyword 'synth -top' is used.

## Various Flop Coding Style and Simulations

![image](https://user-images.githubusercontent.com/69634738/123621440-d2b06880-d828-11eb-885f-ab19cffe5829.png)


# DAY-3
# Combinational and Sequential Optimizations
In order to optimize designs in terms of area and power, optmization techniques are used.

## Combinational Logic Optimizations
To squeeze the logic to get the most optimized designs for area and power savings.
The two types of techniques for combinational logic optimization are
(a)Constant Propagation  (b)Boolean logic optmization

![image](https://user-images.githubusercontent.com/69634738/123624102-d1cd0600-d82b-11eb-9031-ad089111c257.png)

![image](https://user-images.githubusercontent.com/69634738/123624195-e90bf380-d82b-11eb-9a06-9436b15f51dc.png)
The three example file which represent mux are opt_check,opt_check2 and opt_check3.
opt check:
![image](https://user-images.githubusercontent.com/69634738/123624265-fe811d80-d82b-11eb-83bf-986c3dc2803a.png)
optcheck2:
![image](https://user-images.githubusercontent.com/69634738/123625307-43598400-d82d-11eb-901a-51d62fccde11.png)
opt check 3
![image](https://user-images.githubusercontent.com/69634738/123625400-59674480-d82d-11eb-90b4-279f887bcc84.png)

## Sequential Logic Optimizations
The four types of sequential logic optimization are
(a)Sequential constant propagation (b)state optimization (c)Retiming (d)Sequential logic cloning
The tool used is iverilog and file name is dff_const:
![image](https://user-images.githubusercontent.com/69634738/123635448-51ad9d00-d839-11eb-96f0-6ec5a5b24d4a.png)
![image](https://user-images.githubusercontent.com/69634738/123635566-6f7b0200-d839-11eb-9f01-61e1db7c9ee1.png)
![image](https://user-images.githubusercontent.com/69634738/123635642-86215900-d839-11eb-8265-cf50e7e5fb53.png)















