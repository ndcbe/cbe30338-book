# Learning Goals

## Process Historians

**Process historians** are widely used throughout the process industries. The core function is to record and provide access to **time series data** for **process tags**.

The tclab library includes the basic functions of a process historian implemented using `SQLite`, a widely used database for web applications and internet connected devices.

* An instance of the tclab historian requires a list of **data sources**. There is no limit on the number of data sources.
* The default data sources record T1, T2, Q1, and Q2
* Each data source consists of **(tag, function) pair**, where the **tag** is a string that uniquely identifies a time series, and **function**, with no arguments, returns the current value of the tag.
* The tclab historian always records time with the tag "Time"
* Data from the historian can be stored in .csv files, converted to Pandas data frames, or accessed directly from the historian data log.

What you should be able to do:

* Read a list of data sources, and describe what data is recorded.
* Add a tag and a function to a list of data sources.
* Save data from the historian to a .csv file, then load the saved data for analysis.

## State-Space Models

A linear state-space model is written in the form

$$
\begin{align}
\frac{dx}{dt} & = A x + B_u u + B_d d \\
y & = C x
\end{align}
$$

where $x$ is the **state vector** with $n$ elements, $u$ is a vector of manipulable inputs, $d$ is a vector of disturbance inputs, and $y$ is a vector of process measurements. 

* A state-space system is stable if all eigenvalues have negative real parts. 
* If any eigenvalue has a positive real part, then the system is unstable.
* Eigenvalues can be computed with `eigenvalues, _ = np.linalg.eig(A)`
* The negative inverse of an eigenvalue corresponds to a system time constant.

What you should be able to do:

* Convert systems of linear differential equations into state-space form, identifying all relevant vectors and matrices.
* For a given problem, determine if the vectors and matrices are of compatiable dimensions.
* Compute eigenvalues and determine stability.
* Simulate the response of a state-space model to inputs and disturbances.


## State Estimation

State estimation is a form of real-time process analytics employed in control systems. State estimation combines process models with real-time process measurements to provide estimates of process variables that may not be directly measureable.

At each time step $t_k$ there are two calculations to perform:

* **Model Prediction:** Use the model to update the state to the next time step, i.e., $\hat{x}_{k-1} \rightarrow \hat{x}_{k}^{pred}$ with the equation

$$
\begin{align}
\hat{x}_k^{pred} & = \hat{x}_{k-1} + (t_k - t_{k-1}) ( A \hat{x}_{k-1} + B_u u_{k-1} + B_d \hat{d}_{k-1}) \\
\hat{y}_k^{pred} & = C \hat{x}_k^{pred}
\end{align}
$$

* **Measurement Correction:** Use measurement $y_k$ to update $\hat{x}_{k}^{pred} \rightarrow \hat{x}_{k}$ with the equation

$$\hat{x}_{k} = \hat{x}_{k}^{pred} - (t_k - t_{k-1})L (\hat{y}_{k}^{pred} - y_k)$$ 

$L$ is a matrix of observer gains.

The estimation error is given by $e = \hat{x} - {x}$ which satisfies the differential equations

$$
\begin{align}
\frac{de}{dt} & = (A - LC) e + B_d (\hat{d}-d)
\end{align}
$$

where $d$ is the unmeasured disturbance, and $\hat{d}$ is an apriori estimate of $d$. If the estimate is accurate, then $d = \hat{d}$.
