# What is Process Control?

Readings ...

* Astrom and Murray, Chapter 1. {cite}`aastrom2010feedback`
* Brian Douglas, Chapter 1. {cite}`douglas2017fundamentals`
* T. Marlin, Chapters 1 and 2. {cite}`marlin1995process`

The beats ...

1. Important courses in engineering teach universal concepts that can be applied to many situations. Thermodynamics, for example, shows how to use the principles of energy conservation and entropy to analyze and design engines, power systems, chemical equilibrium, biological systems, among many other things. The core concept in this course is **Feedback**. 

1. **Systems** are a collection of interconnected physical and compututional  parts that form a larger and more complex whole. 

1. For any system there are three basic tasks:

    * **System Identification**.  Whaat type of system is this? Can it be modeled mathematically? Can first principles knowledge be incorporated in the model? How can the parameters of the model be determined?
    
    * **Simulation**. Predict system behavior for given inputs and disturances. Does the system reproduce test data? Does the system reproduce data that wasn't used to identify the model?
    
    * **Control**. Given current measurements and uncertainities, determine system inputs needed to achieve a desired response in real time. Control can be computed using control laws 'tuned' to the system, or by optimiziing some measure of system performance.

1. **Feedback** is the use of sensors to regulate the behavior of a system. Feedback is evident in many natural systems, a universal feature of biological systems at all scales, and key to engineering autonomous, self-regulating devices and processes. 

1. **Process control** is the design and application of feedback control to chemical and biomolecular systems to achieve desired behaviors.

1. Examples of feedback ...

    * **Biological Systems:** Insulin/Glucose ![](https://bio.libretexts.org/@api/deki/files/15807/glucose_feedback.png?revision=1) <br>Image Credit: bio.libretexts.org

    * **Biological Systems:** Iron and Oxygen Sensing![](https://els-jbs-prod-cdn.jbs.elsevierhealth.com/cms/attachment/0ea1b4a8-5f44-4b64-a40d-11c8ebd6cdee/gr1.jpg) <br> Image Credit: https://doi.org/10.1016/j.kint.2019.01.003
    
    * **Aerospace Systems:** SpaceX Falcon 9 ![](https://zlsadesign.com/infographic/vehicle/spacex-falcon9-control.png) <br> Image Credit: John Ross, [ZLSA Design](https://zlsadesign.com/)
    
    * **Pharmaceuticals:** Fermentation ![](https://support.industry.siemens.com/cs/images/109478439/fermentation_process.png) <br> Image Credit: [Siemens](https://support.industry.siemens.com/cs/document/109478439/simatic-pcs-7-in-the-pharmaceutical-industry-%E2%80%9Cfermentation%E2%80%9D-(demo-project)?dti=0&lc=en-WW)
    
    * **Automotive:** Autonomous Driving
    
    * **Sports:** Baseball/Softball ... hitting a ball, catching a fly ball, throw and catch from the outfield.
    
1. **Positive Feedback** Positive feedback reinforces change. A desirable behavior for management, training, social situations, bank accounts.

1. **Negative Feedback** Negative feedback suppresses change. Generally what we want for automatic control of processes and devices, in nature and biology.

1. There are two fundamental and potentially conflicting goals of feedback control:

    * **Setpoint Tracking:** Cause a system variable of interest to achieve and track an externally specified value.

    * **Disturbance Rejection:** Maintain a system variable at a desired value regardless of external influences on the system.

1. Setpoints generally come from other control systems. Complex systems usually involve **control heirarchies** to manage complexity and reduce the impact of uncertainty. ![](https://i1.wp.com/www.hisour.com/wp-content/uploads/2018/11/Hierarchical-control-system.jpg) <br> Image Credit: HiSour

1. Disturbances are the uncertainties which control systems are designed to mitigate. Uncertainties are not always subject to classical mathematics.
    * **Measured Disturbances:** Disturbances which can be measured or estimated in advance of their effect on a process system.
    * **Unmeasured Disturbancs:** Disturbances which are not measured.
    
    * **Resolvable Uncertainty:** Uncertainties that can be quantitatively characterized using probabilistic or other methods. Often "long tails". The "known unknowns".
    
    * **Radical Uncertainty:** Cannot be described by probabilistic models. The "unknown unknowns". Outcomes of political events, modes of software failure, changes in customer requirements. This is the human condition.

1. Consequences of feedback.

    * The dynamics of systems under active control are often difficult to understand. Cause and effect may not be what you expect.
    * Feedback control reduces the need for highly accurate or detailed models. Systems become as accurate as their sensors.  
    * The role of feedback is often not understood in social and economic settings.

1. Control is a large interdisciplineary field of ever-growing technical importance. This course will introduce many of the topics in the "Map of Control Theory" by Brian Douglas. ![](../figures/Control_Map_ver5.png) <br> Image Credit: Brian Douglas {cite}`douglas2017fundamentals`
