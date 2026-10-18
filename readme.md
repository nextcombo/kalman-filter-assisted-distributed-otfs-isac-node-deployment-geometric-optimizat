# Kalman Filter-Assisted Distributed OTFS-ISAC Node Deployment: Geometric Optimization Design for Integrated Sensing and Actuation [with Python code]

Kalman Filtering-Assisted Node Deployment for Distributed OTFS-ISAC: A Geometry-Aware Design for the Joint Sensing and Communication
Authors: Jyotsna Rani, Kuntal Deka, Ganesh Prasad, Zilong Liu
Journal Preprint: arXiv:2509.16700v1

Abstract: Integrated Sensing and Communication (ISAC) as a next-generation wireless network core support technology, can achieve both spectrum efficiency and hardware architecture simplification simultaneously. Although traditional single-site ISAC schemes are mature, they suffer from a single observation dimension and weak spatial diversity capabilities, leading to a significant decrease in target tracking reliability under high-speed moving scenarios. Distributed ISAC compensates for this shortcoming through multi-node collaboration, but mainstream OFDM waveforms are highly sensitive to Doppler shift and multipath fading, making it difficult to adapt to high-dynamic vehicle communication environments.
Orthogonal Time Frequency Shift Keying (OTFS) modulation maps signals onto the delay-Doppler domain, where the channel possesses sparse stability characteristics, enabling high-reliable communication and precise perception at the same time. Based on this, this paper extends OTFS modulation to distributed ISAC systems, conducting in-depth research on the optimization of space node deployment issues that are currently less studied.
1.  
Proposes a triangulation-based distributed node deployment framework, utilizing spatial diversity to enhance the accuracy of target positioning, velocity estimation, and communication reach rate. Theoretical derivations are provided to establish the relationship between the estimated error and the geometric structure of the deployment;
2.
Kalman Filter (KF) is integrated into the distributed OTFS-ISAC architecture, three types of tracking algorithms are designed respectively: active perception, passive perception and synergy between perceptions, which can optimize the tracking effect of moving targets.
3  
Deduced the closed-form solution for the covariance of positioning error in a general topology, and proved that the optimal deployment can be achieved by deploying the receiving nodes along orthogonal coordinate axes.
4  
Numerical simulation verification: The framework of this paper can significantly reduce the root mean square error (RMSE) and bit error rate (BER), clarifying the performance trade-off between perception accuracy and communication reliability.
The results of this paper prove that the node geometric optimization deployment scheme, which integrates Kalman filtering, can enable the distributed OTFS integrated system to achieve high performance and stable operation in high-speed dynamic wireless scenarios.
III. Research Background and Introduction
Traditional OFDM waveforms have a fatal flaw in high-speed moving scenarios: Doppler frequency shift and multipath fading can severely degrade communication and perception performance. OTFS modulation processes signals in the time-delay and Doppler domains, with a sparse channel that naturally adapts to high dynamic vehicle environments. It can simultaneously achieve high-precision radar detection and stable data transmission.
However, the implementation of OTFS integrated perception still faces multiple challenges: continuous tracking of mobile vehicles, communication stability under strong Doppler channels, high-precision estimation of multi-target speeds, and precise positioning in multipath environments; meanwhile, single-center node coverage is limited, and the cost of large-scale antenna array hardware and computation is too high. Distributed OTFS-ISAC adopts a low-complexity node collaboration to expand coverage, enhance collaborative perception, and reduce the cost per node, perfectly addressing these issues. This paper further improves the comprehensive performance of distributed OTFS-ISAC through Kalman filtering.
3.2 Existing Research Review
(1) Single-site Integrated Sensing and Communications (ISAC) hardware is cost-effective and has high spectral efficiency. Extensive research has combined MIMO arrays to achieve joint estimation of distance, angle, and velocity, adapting to the Vehicular Internet of Things (V2X) standards. However, its shortcomings are significant: it only observes from a single perspective, lacking spatial diversity, and in high-speed scenarios, Doppler and multipath can significantly reduce target tracking stability, necessitating distributed architecture optimization.
(2) Distributed ISAC with multiple base stations and vehicle terminals for integrated sensing and communication relies on spatial diversity to enhance positioning accuracy, serving as the mainstream solution to address the deficiencies of single-site ISAC. Current research focuses on uplink collaborative waveform design, resource allocation, time-division cooperative V2X, and multistatic radar collaboration, unifying inter-sensor performance tradeoffs through mutual information modeling. However, most existing distributed ISACs use OFDM waveforms, which have poor time-varying channel robustness and suffer severe performance degradation in high-speed scenarios.
(3) The Integrated OTFS for sensing and communication (OTFS-ISAC) based on OTFS leverages its advantages in delay and Doppler domain anti-Doppler and anti-multipath capabilities, becoming an optimal waveform for next-generation ISAC. Current research focuses on precoding in the DD domain, fractional-order delay Doppler estimation algorithms, uncellular large-scale MIMO power allocation, multistatic OTFS target association positioning, and super-resolution ranging and speed measurement, verifying the performance advantages of OTFS-ISAC. A research gap exists: there is almost no literature combining Kalman filtering with distributed OTFS-ISAC optimal space node deployment strategies, as node placement directly determines perception coverage, positioning accuracy, and communication quality; simultaneously, the gain of Kalman filtering for mobile target temporal tracking has not yet been combined with node geometric optimization.
3.3 The motivation of this study and the core innovations: Existing distributed OTFS-ISAC research focuses on waveform and resource allocation, ignoring node spatial deployment optimization. The Kalman filtering temporal tracking advantages are not combined with the node geometric topology. In response to this blank, this paper proposes a Kalman Filter-assisted geometric optimization deployment scheme for nodes. The core innovation is as follows:
1  
Construct a complete distributed OTFS-ISAC system topology, derive the OTFS emission waveform and reception signal processing flow, respectively establish two sets of parameter estimation algorithms for active perception and passive transduction synergy, realize the joint solution of target distance, radial velocity, communication rate.
2  
Propose a geometric triangulation framework, using multi-node spatial diversity to improve the accuracy of target position and velocity estimation. Prove by lemma: maximizing triangle coverage area can minimize positioning error; Inferred proof: The optimal topology can be achieved by setting the receiving nodes along orthogonal axes.
3  
Deduced the closed-form expressions of covariance trace and maximum eigenvalue for target position estimation in random deployment general topology; proved that multi-antenna orthogonal axis node deployment can reduce the positioning error to (N) of single antenna scheme.
4  
Based on the related stochastic walk (CRW) continuous motion model, three types of Kalman filter algorithms are designed after quantization: KF active perception optimization and KF passive transduction synergistic algorithm. The time complexity of these three algorithms is analyzed in detail.
5  
Large-scale Numerical Simulation: Comparing RMSE, speed RMSE, communication BER under Kalman filtering, random / optimal node deployment, different antenna numbers, and different SNRs for positioning, velocity, and communication performance. Quantization perception - trade-off of communication performance.
IV. Core Methods and Principles
Active Perception: The anchor node emits a known detection signal, and all receiving nodes utilize the complete waveform to achieve dual-station collaborative perception.
Passive Perception: The anchor node only transmits business communication data, while the receiving end only knows the pilot frequency, completing communication demodulation and environmental perception simultaneously without additional detection signals, saving energy and eliminating interference.
The channel adopts a dual-expanded time-frequency dispersion channel, with all signals transmitted based on OTFS modulation.
4.2 OTFS Signal Transmission and Reception Principle (1) Transmitter OTFS Signal Construction:
QAM information symbol vector is reshaped into a two-dimensional matrix of delay - Doppler, representing the number of delay intervals and Doppler intervals;
2
Insert a single peak pilot matrix, superimposed to generate an integrated DD domain matrix;
3
Transform through the inverse Singular Finite Fourier Transform (ISFFT) to the time-frequency domain, followed by pulse shaping filtering to produce the time-domain transmission signal;
4
Signal dimensionality is bounded by bandwidth, frame duration, delay resolution, and Doppler resolution.
(2) Receiver Signal Processing: The received signal is a sum of multipath channels with Gaussian noise, each path introduces independent channel gain, circular delay, Doppler offset. The receiver performs the inverse operation of transmission: restores the time-domain signal into an DD domain matrix, separates multipath components, obtains an DD domain reception vector for subsequent channel and target parameter estimation.
4.3 Two Perception Working Modes Algorithms (1) Active Perception Parameter Estimation Algorithm: The transmitter receives complete data waveforms, and the receiver has full knowledge of them. A maximum likelihood estimation least square cost function is constructed using a serial multipath estimation algorithm:
1
Two-dimensional delay - Doppler grid cross-correlation search is conducted to extract the strongest path delay and Doppler;
2
Closed-form solution for corresponding path channel complex gain;
3
From the received signal, paths already estimated are cancelled, iteratively estimating remaining multipaths;
4
Through delay and Doppler conversion to estimate target distance and radial velocity; complexity: single receiver single path, overall complexity linearly grows with the number of nodes and paths.
(2) The passive-active synergy iterative algorithm for receivers only knows the pilot signal, with information data as interference. It adopts an inner and outer double-layer iterative optimization:
1  
Outer iteration: Alternately perform communication data demodulation and refined perception of channel parameters;
2  
Inner gradient descent iteration: Solve communication symbols using the regularized MMSE criterion, set a convergence threshold to stop iterations;
3  
The complete DD domain signal (data + pilot) after demodulation is used for re-estimation of delay, Doppler, and channel gain at high precision;
4  
After the channel parameters converge, output the communication bits and target distance/speed; Advantage: No need for dedicated detection waveforms, parallel execution of communication perception, suitable for low-power terminals.
4.4 Multi-node collaborative trilateration and speed measurement utilize anchor nodes + dual receiving nodes to form a triangle, based on multi-station measured distances to construct a linear equation system, solving the target's two-dimensional coordinates; Use the radial velocity observations from each node to construct a velocity projection matrix to solve the true two-dimensional velocity of the target.
1  
Multi-trilateration observation integration scheme: Average the trilateration results of all nodes, suppressing random noise;
2  
Near-neighbor filtering optimization: Exclude abnormal estimation values caused by geometric distortions (three points are approximately collinear or baseline is too close), retaining only spatially consistent observation results for average, significantly reducing the impact of coarse errors.
4.5 Node geometric deployment optimal theory (core geometric lemma):
Lemma 1: The covariance trace and maximum eigenvalue of the target position estimation estimate are determined by the area of the triangle formed by the anchor node + dual receiving nodes, maximizing the triangle area can minimize the positioning error;
2  
Lemma 2: By placing the receiving nodes at X, Y orthogonal coordinate axes within a limited area, maximizing the area of a right-angled triangle can achieve near-optimal deployment;
3  
Lemma 4: When both the anchor node and two orthogonal axis receiving nodes are equipped with N independent antennas, the positioning estimation error can be reduced to that of the original scheme, and the accuracy gain increases cubically with the number of antennas.
4.6 The CRW-related stochastic walk Kalman filtering tracking algorithm is designed for the smooth and continuous motion characteristics of vehicles and drones, using the Ornstein-Uhlenbeck process to construct a continuous stochastic walk (CRW) motion model. After discretization, a Kalman filtering time series tracking framework is established:
1  
Target state vector: Horizontal
Sit
Specs
Long
Sit
Specs
To
Fast
Degree
To
Fast
Degree
;   
2  
State prediction: Based on historical position and velocity, iteratively predicts the next moment's target state.
3  
Measurement update: The target position and velocity obtained by triangulation are used as observation values, and the prediction values are corrected with Kalman gain.
4  
Three sets of complete KF algorithms:
Algorithm 1: Basic Kalman Filter Universal Iterative Function;
Algorithm 2: KF enhances active perception, temporal smoothing eliminates single-time perception noise;
Algorithm 3: KF enhanced passive-active synergy, iterative demodulation + sequential tracking integration; Kalman filter core gain: balance measurement noise and motion prediction noise to avoid instantaneous anomaly observations causing tracking jumps, continuously smoothing the target trajectory.
5.1 Simulation Core Parameters: Carrier at 30GHz, Millimeter Wave, OTF parameters M=256, Doppler grid N=16, 4QAM modulation, square 400m test area with 4 moving targets, single node antenna number adjustable from 1 to 10, Signal-to-Noise Ratio -20dB~20dB.
5.2 Key Simulation Conclusions 1
Kalman Filter significantly enhances perception accuracy. Without KF active perception, the mean positioning RMSE is 25.06m at a 0dB signal-to-noise ratio (SNR), and the velocity RMSE is 31.63m/s; however, with the introduction of KF, these values are reduced to 19.76m and 25.46m/s respectively. The effect of error suppression by KF becomes more pronounced as the SNR decreases and the number of targets increases.
2  
The accuracy of orthogonal antenna deployments has increased by a cubic power, with the RMSE for single-antenna positioning dropping to approximately 0.23m when using 10 antennas at a single node. As the number of antennas increases, errors rapidly decrease, demonstrating that orthogonal optimal deployment significantly outperforms random placement.
3  
The active perception performance is superior to the passive transceiver integrated active perception with complete waveform known, and the time delay Doppler estimation accuracy is higher. The passive only relies on pilot iteration demodulation, which has inherent estimation loss, and the positioning error under the same antenna and signal-to-noise ratio is higher than that of active perception.
4  
Optimal geometric deployment + KF joint optimization for communication error rate of 8dB with a signal-to-noise ratio, compared to existing literature benchmarks: random deployment ISAC BER improvement of 64.41%, orthogonal optimal deployment ISAC improvement of 79.91%; KF assisted orthogonal optimal ISAC error rate improvement of up to 87.37%; the relative advantage of this scheme increases with an increase in the number of antennas.
5  
The determinant role of node deployment geometry is that random placement of receiving nodes will form a large number of narrow triangular observation areas, significantly increasing the positioning error. Maximizing the triangle coverage area along orthogonal coordinate axes can reduce the estimation lower bound from the geometric foundation, which is a key method to improve sensory performance at low cost.
5.3 Summary of the full text
This paper constructs a complete Kalman Filter-assisted Geometric Optimization Distributed OTFS-ISAC framework, which fully covers the entire process of OTFS signal reception and transmission, active / passive perception, multi-node triangular collaborative positioning, and CRW-KF time-series tracking.
2  
Geometric theory proves: The optimal deployment scheme is to deploy the receiving nodes along orthogonal coordinate axes, maximizing triangular observation area. Multi-antenna configuration can reduce positioning error by cubic order.
3  
Design three types of Kalman filtering iterative algorithms, respectively adaptive to active perception and passive sensing collaborative scenarios. Through temporal smoothing, effectively suppress transient perception noise, synchronously optimize the accuracy of positioning and speed measurement and communication error rate.
4  
Numerical simulation verification: Orthogonal optimal node deployment integrated with Kalman filtering, compared to random deployment and no KF baseline schemes, simultaneously achieves lower position RMSE and BER. It possesses strong practicality in high-speed vehicle and high Doppler dynamic scenarios;
5
Research value: This study fills the research gap of distributed OTFS integrated tactile and auditory "node geometric deployment + time-series tracking filtering" joint optimization, providing a low-complexity, high-performance engineering design concept for autonomous driving connected vehicle network and millimeter wave distributed radar integrated tactile and auditory network.
Sixth, at the end of this summary, many people may wonder: Why is the OTFS + distributed multi-node + Kalman filtering solution more suitable for autonomous driving than other integrated tactile and auditory solutions?
1
OFDM is afraid of the Doppler shift caused by high-speed movement, vehicles moving quickly can lead to poor radar detection and communication transmission, while OTFS processes signals in the time delay Doppler domain, inherently resistant to high speed;
2
Single base station radar can only observe vehicles from one angle, easy to lose targets under obstruction and multipath environments, cooperative triangulation of multiple distributed nodes enhances robustness in multiple perspectives;
3
Nodes placed randomly have poor effects, mathematically proving that placing receiving nodes in two orthogonal directions maximizes the observation area, directly reducing the positioning error;
4
Single radar observation is easily affected by noise and jumps, combined with the continuous motion pattern of vehicles, Kalman filtering smooths the trajectory and continuously tracks moving vehicles stably; The entire solution does not need to significantly increase hardware costs, but through node placement optimization + backend time-series filtering algorithm, it improves both core capabilities of autonomous driving's vehicle-to-vehicle communication and environmental radar detection, making it a feasible implementation plan for next-generation intelligent transportation mmWave networks.

## Images

![Kalman Filter-Assisted Deployment of Distributed OTFS-ISAC Nodes: Geometric Optimization Design for Integrated Sensing and Actuation [with Python code]](cover.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
