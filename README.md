# libsnark-demo

考虑到国内`github`网络稳定，本项目将所有依赖集成，无需再次`submodule update`



### 克隆项目

```bash
git clone git@github.com:Trusted-Federal-Learning/libsnark-demo.git
cd ./libsnark-demo
```



### 安装环境

不同系统有不同安装环境的方式，以下列举常见系统的环境安装方式：

- Debian 10 (buster), Ubuntu 18.04 LTS, Ubuntu 20.04 LTS:

  ```bash
  sudo apt install build-essential cmake git libgmp3-dev libprocps-dev python3-markdown libboost-program-options-dev libssl-dev python3 pkg-config
  ```

- Ubuntu 16.04 LTS:

  ```bash
  sudo apt-get install build-essential cmake git libgmp3-dev libprocps4-dev python-markdown libboost-all-dev libssl-dev
  ```

- Ubuntu 14.04 LTS:

  ```bash
  sudo apt-get install build-essential cmake git libgmp3-dev libprocps3-dev python-markdown libboost-all-dev libssl-dev
  ```

- Fedora 31:

  ```bash
  sudo dnf install gcc-c++ cmake make git gmp-devel procps-ng-devel boost-devel openssl-devel python3-markdown
  ```

- Fedora 21 through 23:

  ```bash
  sudo yum install gcc-c++ cmake make git gmp-devel procps-ng-devel python2-markdown
  ```

- Fedora 20:

  ```bash
  sudo yum install gcc-c++ cmake make git gmp-devel procps-ng-devel python-markdown
  ```



### 编译

创建`build`目录，并在`build`目录下执行`cmake`和`make`

```bash
mkdir build && cd build && cmake ..
make
```



### 核心文件

* `R1CS`电路文件在`./src`中
* 编译目录：`./build`
* 编译方式：在`build`目录下执行`make`命令
* 编译生成的可执行文件在`./build/src`中



### 测试

编译

```bash
cd ./build
# 进入编译目录

make
# make 进行编译

./src/test
# 执行可执行文件
```



测试结果：

```bash
(enter) Call to r1cs_gg_ppzksnark_generator	[             ]	(1622710624.4394s x0.00 from start)
  (enter) Call to r1cs_constraint_system::swap_AB_if_beneficial	[             ]	(1622710624.4395s x0.00 from start)
    (enter) Estimate densities                 	[             ]	(1622710624.4395s x0.00 from start)
      * Non-zero A-count (estimate): 5
      * Non-zero B-count (estimate): 2
    (leave) Estimate densities                 	[0.0000s x1.00]	(1622710624.4395s x0.00 from start)
    Swap is not beneficial, not performing
  (leave) Call to r1cs_constraint_system::swap_AB_if_beneficial	[0.0000s x0.93]	(1622710624.4395s x0.00 from start)
  (enter) Call to r1cs_to_qap_instance_map_with_evaluation	[             ]	(1622710624.4401s x0.00 from start)
    (enter) Compute evaluations of A, B, C, H at t	[             ]	(1622710624.4402s x0.00 from start)
    (leave) Compute evaluations of A, B, C, H at t	[0.0001s x0.99]	(1622710624.4402s x0.00 from start)
  (leave) Call to r1cs_to_qap_instance_map_with_evaluation	[0.0002s x1.00]	(1622710624.4403s x0.00 from start)
  * QAP number of variables: 5
  * QAP pre degree: 4
  * QAP degree: 6
  * QAP number of input variables: 1
  (enter) Compute query densities            	[             ]	(1622710624.4403s x0.00 from start)
  (leave) Compute query densities            	[0.0000s x1.04]	(1622710624.4403s x0.00 from start)
  (enter) Compute gamma_ABC for R1CS verification key	[             ]	(1622710624.4403s x0.00 from start)
  (leave) Compute gamma_ABC for R1CS verification key	[0.0000s x1.04]	(1622710624.4403s x0.00 from start)
  (enter) Compute L query for R1CS proving key	[             ]	(1622710624.4403s x0.00 from start)
  (leave) Compute L query for R1CS proving key	[0.0000s x1.07]	(1622710624.4403s x0.00 from start)
  (enter) Generating G1 MSM window table     	[             ]	(1622710624.4403s x0.00 from start)
    Choosing window size 3 for 13 elements
    * G1 window: 3
  (leave) Generating G1 MSM window table     	[0.0015s x1.00]	(1622710624.4418s x0.00 from start)
  (enter) Generating G2 MSM window table     	[             ]	(1622710624.4419s x0.00 from start)
    Choosing window size 1 for 2 elements
    * G2 window: 1
  (leave) Generating G2 MSM window table     	[0.0041s x1.00]	(1622710624.4460s x0.00 from start)
  (enter) Generate R1CS proving key          	[             ]	(1622710624.4461s x0.00 from start)
    (enter) Generate queries                   	[             ]	(1622710624.4496s x0.00 from start)
      (enter) Compute the A-query                	[             ]	(1622710624.4497s x0.00 from start)
      . DONE!
      (leave) Compute the A-query                	[0.0005s x1.00]	(1622710624.4502s x0.00 from start)
      (enter) Compute the B-query                	[             ]	(1622710624.4502s x0.00 from start)
      Non-zero coordinate count: 2/6 (33.33%)
      (leave) Compute the B-query                	[0.0014s x1.00]	(1622710624.4516s x0.00 from start)
      (enter) Compute the H-query                	[             ]	(1622710624.4516s x0.00 from start)
      . DONE!
      (leave) Compute the H-query                	[0.0004s x1.00]	(1622710624.4521s x0.00 from start)
      (enter) Compute the L-query                	[             ]	(1622710624.4521s x0.00 from start)
      . DONE!
      (leave) Compute the L-query                	[0.0004s x1.00]	(1622710624.4524s x0.00 from start)
    (leave) Generate queries                   	[0.0028s x1.00]	(1622710624.4524s x0.00 from start)
  (leave) Generate R1CS proving key          	[0.0064s x1.00]	(1622710624.4524s x0.00 from start)
  (enter) Generate R1CS verification key     	[             ]	(1622710624.4524s x0.00 from start)
    (enter) Call to alt_bn128_ate_reduced_pairing	[             ]	(1622710624.4525s x0.00 from start)
      (enter) Call to alt_bn128_ate_pairing      	[             ]	(1622710624.4525s x0.00 from start)
        (enter) Call to alt_bn128_ate_precompute_G1	[             ]	(1622710624.4525s x0.00 from start)
        (leave) Call to alt_bn128_ate_precompute_G1	[0.0000s x1.05]	(1622710624.4525s x0.00 from start)
        (enter) Call to alt_bn128_ate_precompute_G2	[             ]	(1622710624.4525s x0.00 from start)
        (leave) Call to alt_bn128_ate_precompute_G2	[0.0004s x1.00]	(1622710624.4529s x0.00 from start)
        (enter) Call to alt_bn128_ate_miller_loop  	[             ]	(1622710624.4529s x0.00 from start)
        (leave) Call to alt_bn128_ate_miller_loop  	[0.0010s x1.00]	(1622710624.4539s x0.00 from start)
      (leave) Call to alt_bn128_ate_pairing      	[0.0015s x1.00]	(1622710624.4540s x0.00 from start)
      (enter) Call to alt_bn128_final_exponentiation	[             ]	(1622710624.4540s x0.00 from start)
        (enter) Call to alt_bn128_final_exponentiation_first_chunk	[             ]	(1622710624.4540s x0.00 from start)
        (leave) Call to alt_bn128_final_exponentiation_first_chunk	[0.0000s x1.01]	(1622710624.4540s x0.00 from start)
        (enter) Call to alt_bn128_final_exponentiation_last_chunk	[             ]	(1622710624.4540s x0.00 from start)
          (enter) Call to alt_bn128_exp_by_neg_z     	[             ]	(1622710624.4540s x0.00 from start)
          (leave) Call to alt_bn128_exp_by_neg_z     	[0.0005s x1.00]	(1622710624.4546s x0.00 from start)
          (enter) Call to alt_bn128_exp_by_neg_z     	[             ]	(1622710624.4546s x0.00 from start)
          (leave) Call to alt_bn128_exp_by_neg_z     	[0.0005s x1.00]	(1622710624.4551s x0.00 from start)
          (enter) Call to alt_bn128_exp_by_neg_z     	[             ]	(1622710624.4552s x0.00 from start)
          (leave) Call to alt_bn128_exp_by_neg_z     	[0.0005s x1.00]	(1622710624.4557s x0.00 from start)
        (leave) Call to alt_bn128_final_exponentiation_last_chunk	[0.0018s x1.00]	(1622710624.4558s x0.00 from start)
      (leave) Call to alt_bn128_final_exponentiation	[0.0019s x1.00]	(1622710624.4558s x0.00 from start)
    (leave) Call to alt_bn128_ate_reduced_pairing	[0.0034s x1.00]	(1622710624.4558s x0.00 from start)
    (enter) Encode gamma_ABC for R1CS verification key	[             ]	(1622710624.4570s x0.00 from start)
      . DONE!
    (leave) Encode gamma_ABC for R1CS verification key	[0.0005s x1.00]	(1622710624.4574s x0.00 from start)
  (leave) Generate R1CS verification key     	[0.0050s x1.00]	(1622710624.4574s x0.00 from start)
(leave) Call to r1cs_gg_ppzksnark_generator	[0.0180s x1.00]	(1622710624.4575s x0.00 from start)
* G1 elements in PK: 22
* Non-zero G1 elements in PK: 18
* G2 elements in PK: 7
* Non-zero G2 elements in PK: 3
* PK size in bits: 6245
* G1 elements in VK: 1
* G2 elements in VK: 2
* GT elements in VK: 1
* VK size in bits: 1592
(enter) Call to r1cs_gg_ppzksnark_prover   	[             ]	(1622710624.4575s x0.00 from start)
  (enter) Compute the polynomial H           	[             ]	(1622710624.4575s x0.00 from start)
    (enter) Call to r1cs_to_qap_witness_map    	[             ]	(1622710624.4575s x0.00 from start)
      (enter) Compute evaluation of polynomials A, B on set S	[             ]	(1622710624.4576s x0.00 from start)
      (leave) Compute evaluation of polynomials A, B on set S	[0.0000s x1.00]	(1622710624.4576s x0.00 from start)
      (enter) Compute coefficients of polynomial A	[             ]	(1622710624.4576s x0.00 from start)
      (leave) Compute coefficients of polynomial A	[0.0000s x1.01]	(1622710624.4576s x0.00 from start)
      (enter) Compute coefficients of polynomial B	[             ]	(1622710624.4576s x0.00 from start)
      (leave) Compute coefficients of polynomial B	[0.0000s x1.02]	(1622710624.4576s x0.00 from start)
      (enter) Compute ZK-patch                   	[             ]	(1622710624.4576s x0.00 from start)
      (leave) Compute ZK-patch                   	[0.0000s x1.07]	(1622710624.4576s x0.00 from start)
      (enter) Compute evaluation of polynomial A on set T	[             ]	(1622710624.4576s x0.00 from start)
      (leave) Compute evaluation of polynomial A on set T	[0.0000s x1.06]	(1622710624.4576s x0.00 from start)
      (enter) Compute evaluation of polynomial B on set T	[             ]	(1622710624.4576s x0.00 from start)
      (leave) Compute evaluation of polynomial B on set T	[0.0000s x1.06]	(1622710624.4577s x0.00 from start)
      (enter) Compute evaluation of polynomial H on set T	[             ]	(1622710624.4577s x0.00 from start)
        (enter) Compute evaluation of polynomial C on set S	[             ]	(1622710624.4577s x0.00 from start)
        (leave) Compute evaluation of polynomial C on set S	[0.0000s x1.09]	(1622710624.4577s x0.00 from start)
        (enter) Compute coefficients of polynomial C	[             ]	(1622710624.4577s x0.00 from start)
        (leave) Compute coefficients of polynomial C	[0.0000s x1.02]	(1622710624.4577s x0.00 from start)
        (enter) Compute evaluation of polynomial C on set T	[             ]	(1622710624.4577s x0.00 from start)
        (leave) Compute evaluation of polynomial C on set T	[0.0000s x0.98]	(1622710624.4577s x0.00 from start)
        (enter) Divide by Z on set T               	[             ]	(1622710624.4578s x0.00 from start)
        (leave) Divide by Z on set T               	[0.0000s x1.02]	(1622710624.4578s x0.00 from start)
      (leave) Compute evaluation of polynomial H on set T	[0.0001s x1.00]	(1622710624.4578s x0.00 from start)
      (enter) Compute coefficients of polynomial H	[             ]	(1622710624.4578s x0.00 from start)
      (leave) Compute coefficients of polynomial H	[0.0000s x1.04]	(1622710624.4578s x0.00 from start)
      (enter) Compute sum of H and ZK-patch      	[             ]	(1622710624.4578s x0.00 from start)
      (leave) Compute sum of H and ZK-patch      	[0.0000s x1.04]	(1622710624.4578s x0.00 from start)
    (leave) Call to r1cs_to_qap_witness_map    	[0.0003s x1.00]	(1622710624.4578s x0.00 from start)
  (leave) Compute the polynomial H           	[0.0004s x1.00]	(1622710624.4579s x0.00 from start)
  (enter) Compute the proof                  	[             ]	(1622710624.4580s x0.00 from start)
    (enter) Compute evaluation to A-query      	[             ]	(1622710624.4580s x0.00 from start)
    (enter) Process scalar vector              	[             ]	(1622710624.4580s x0.00 from start)
      * Elements of w skipped: 0 (0.00%)
      * Elements of w processed with special addition: 1 (16.67%)
      * Elements of w remaining: 5 (83.33%)
    (leave) Process scalar vector              	[0.0000s x1.05]	(1622710624.4580s x0.00 from start)
    (leave) Compute evaluation to A-query      	[0.0001s x1.01]	(1622710624.4581s x0.00 from start)
    (enter) Compute evaluation to B-query      	[             ]	(1622710624.4581s x0.00 from start)
    (enter) Process scalar vector              	[             ]	(1622710624.4581s x0.00 from start)
      * Elements of w skipped: 0 (0.00%)
      * Elements of w processed with special addition: 1 (50.00%)
      * Elements of w remaining: 1 (50.00%)
    (leave) Process scalar vector              	[0.0000s x1.03]	(1622710624.4581s x0.00 from start)
    (leave) Compute evaluation to B-query      	[0.0001s x1.02]	(1622710624.4582s x0.00 from start)
    (enter) Compute evaluation to H-query      	[             ]	(1622710624.4582s x0.00 from start)
    (leave) Compute evaluation to H-query      	[0.0009s x1.00]	(1622710624.4591s x0.00 from start)
    (enter) Compute evaluation to L-query      	[             ]	(1622710624.4591s x0.00 from start)
    (enter) Process scalar vector              	[             ]	(1622710624.4592s x0.00 from start)
      * Elements of w skipped: 0 (0.00%)
      * Elements of w processed with special addition: 0 (0.00%)
      * Elements of w remaining: 4 (100.00%)
    (leave) Process scalar vector              	[0.0000s x1.03]	(1622710624.4592s x0.00 from start)
    (leave) Compute evaluation to L-query      	[0.0000s x0.99]	(1622710624.4592s x0.00 from start)
  (leave) Compute the proof                  	[0.0038s x1.00]	(1622710624.4618s x0.00 from start)
(leave) Call to r1cs_gg_ppzksnark_prover   	[0.0044s x1.00]	(1622710624.4619s x0.00 from start)
* G1 elements in proof: 2
* G2 elements in proof: 1
* Proof size in bits: 1019
(enter) Call to r1cs_gg_ppzksnark_verifier_strong_IC	[             ]	(1622710624.4619s x0.00 from start)
  (enter) Call to r1cs_gg_ppzksnark_verifier_process_vk	[             ]	(1622710624.4619s x0.00 from start)
    (enter) Call to alt_bn128_ate_precompute_G2	[             ]	(1622710624.4619s x0.00 from start)
    (leave) Call to alt_bn128_ate_precompute_G2	[0.0005s x0.93]	(1622710624.4624s x0.00 from start)
    (enter) Call to alt_bn128_ate_precompute_G2	[             ]	(1622710624.4624s x0.00 from start)
    (leave) Call to alt_bn128_ate_precompute_G2	[0.0004s x1.00]	(1622710624.4628s x0.00 from start)
  (leave) Call to r1cs_gg_ppzksnark_verifier_process_vk	[0.0010s x0.96]	(1622710624.4628s x0.00 from start)
  (enter) Call to r1cs_gg_ppzksnark_online_verifier_strong_IC	[             ]	(1622710624.4628s x0.00 from start)
    (enter) Call to r1cs_gg_ppzksnark_online_verifier_weak_IC	[             ]	(1622710624.4628s x0.00 from start)
      (enter) Accumulate input                   	[             ]	(1622710624.4628s x0.00 from start)
      (leave) Accumulate input                   	[0.0000s x1.03]	(1622710624.4629s x0.00 from start)
      (enter) Check if the proof is well-formed  	[             ]	(1622710624.4629s x0.00 from start)
      (leave) Check if the proof is well-formed  	[0.0000s x1.05]	(1622710624.4629s x0.00 from start)
      (enter) Online pairing computations        	[             ]	(1622710624.4629s x0.00 from start)
        (enter) Check QAP divisibility             	[             ]	(1622710624.4629s x0.00 from start)
          (enter) Call to alt_bn128_ate_precompute_G1	[             ]	(1622710624.4629s x0.00 from start)
          (leave) Call to alt_bn128_ate_precompute_G1	[0.0000s x1.05]	(1622710624.4629s x0.00 from start)
          (enter) Call to alt_bn128_ate_precompute_G2	[             ]	(1622710624.4629s x0.00 from start)
          (leave) Call to alt_bn128_ate_precompute_G2	[0.0004s x1.00]	(1622710624.4633s x0.00 from start)
          (enter) Call to alt_bn128_ate_precompute_G1	[             ]	(1622710624.4634s x0.00 from start)
          (leave) Call to alt_bn128_ate_precompute_G1	[0.0000s x0.99]	(1622710624.4634s x0.00 from start)
          (enter) Call to alt_bn128_ate_precompute_G1	[             ]	(1622710624.4634s x0.00 from start)
          (leave) Call to alt_bn128_ate_precompute_G1	[0.0000s x1.03]	(1622710624.4634s x0.00 from start)
          (enter) Call to alt_bn128_ate_miller_loop  	[             ]	(1622710624.4634s x0.00 from start)
          (leave) Call to alt_bn128_ate_miller_loop  	[0.0010s x1.00]	(1622710624.4644s x0.00 from start)
          (enter) Call to alt_bn128_ate_double_miller_loop	[             ]	(1622710624.4645s x0.00 from start)
          (leave) Call to alt_bn128_ate_double_miller_loop	[0.0017s x1.00]	(1622710624.4661s x0.00 from start)
          (enter) Call to alt_bn128_final_exponentiation	[             ]	(1622710624.4662s x0.00 from start)
            (enter) Call to alt_bn128_final_exponentiation_first_chunk	[             ]	(1622710624.4662s x0.00 from start)
            (leave) Call to alt_bn128_final_exponentiation_first_chunk	[0.0000s x1.01]	(1622710624.4662s x0.00 from start)
            (enter) Call to alt_bn128_final_exponentiation_last_chunk	[             ]	(1622710624.4663s x0.00 from start)
              (enter) Call to alt_bn128_exp_by_neg_z     	[             ]	(1622710624.4663s x0.00 from start)
              (leave) Call to alt_bn128_exp_by_neg_z     	[0.0005s x1.00]	(1622710624.4668s x0.00 from start)
              (enter) Call to alt_bn128_exp_by_neg_z     	[             ]	(1622710624.4668s x0.00 from start)
              (leave) Call to alt_bn128_exp_by_neg_z     	[0.0005s x1.00]	(1622710624.4673s x0.00 from start)
              (enter) Call to alt_bn128_exp_by_neg_z     	[             ]	(1622710624.4674s x0.00 from start)
              (leave) Call to alt_bn128_exp_by_neg_z     	[0.0005s x1.00]	(1622710624.4679s x0.00 from start)
            (leave) Call to alt_bn128_final_exponentiation_last_chunk	[0.0017s x1.00]	(1622710624.4680s x0.00 from start)
          (leave) Call to alt_bn128_final_exponentiation	[0.0019s x1.00]	(1622710624.4680s x0.00 from start)
        (leave) Check QAP divisibility             	[0.0052s x1.00]	(1622710624.4681s x0.00 from start)
      (leave) Online pairing computations        	[0.0052s x1.00]	(1622710624.4681s x0.00 from start)
    (leave) Call to r1cs_gg_ppzksnark_online_verifier_weak_IC	[0.0052s x1.00]	(1622710624.4681s x0.00 from start)
  (leave) Call to r1cs_gg_ppzksnark_online_verifier_strong_IC	[0.0052s x1.00]	(1622710624.4681s x0.00 from start)
(leave) Call to r1cs_gg_ppzksnark_verifier_strong_IC	[0.0062s x0.99]	(1622710624.4681s x0.00 from start)
Number of R1CS constraints: 4
Primary (public) input: 1
35

Auxiliary (private) input: 4
3
9
27
30

Verification status: 1
```





## Reference

- https://github.com/sec-bit/libsnark_abc
- https://github.com/scipr-lab/libsnark