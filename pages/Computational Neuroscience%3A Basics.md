- # Agenda #todolist
	- ### View Lectures
		- DONE View Lecture 1
		- DONE [#A] View Lecture 2
		- DONE [#A] View Lecture 3
	- ### Revies Lectures
		- DONE [#B] Review Lecture 1
		- DONE [#B] Review Lecture 2
		- DONE [#B] Review Lecture 3
- # The Basics - A reminder
	- ## Literature (all of this is very mathematical!)
	  collapsed:: true
		- **General Theoretical Neuroscience:**
		  collapsed:: true
			- Theoretical Neuroscience“, P.Dayan and L. Abbott, MIT Press (there used to be a version of this on the
			  internet)
			- „Spiking Neuron Models“, W. Gerstner & W.M. Kistler, Cambridge University Press. (there is a version on
			  the internet)
		- **Neural Coding Issues:**
		  collapsed:: true
			- „Spikes“ F. Rieke, D. Warland, R. de Ruyter v. Steveninck, W. Bialek, MIT Press
		- **Artificial Neural Networks:**
		  collapsed:: true
			- „Konnektionismus“, G. Dorffner, B.G. Teubner Verlg. Stuttgart
			- „Fundamentals of Artificial Neural Networks“, M.H. Hassoun, MIT Press
		- **Hodgkin Huxley Model:**
		  collapsed:: true
			- See above „Spiking Neuron Models“, W. Gerstner & W.M. Kistler, Cambridge
			  University Press.
		- **Learning and Plasticity:**
		  collapsed:: true
			- See above „Spiking Neuron Models“, W. Gerstner & W.M. Kistler, Cambridge University Press.
		- **Calculating with Neurons:** Has been compiled from many different sources.
		- **Maps:** Has been compiled from many different sources.
		- **General Neuro:** *(for a overview of concepts)*
		  collapsed:: true
			- Kandel, Schwartz, Jessel: Principles of Neural Science
			- *Schmidt, Schaibl:, Neuro- und Sinnesphysiologie*
	- ## Brain, Maps, Areas, Networks, Neurons, and Synapses
	  collapsed:: true
		- Computational Neuroscience:
		  collapsed:: true
			- Qualitative Methods - How to describe brain functions?
		- Interdisciplinary
		  collapsed:: true
			- Fundamental Sciences: Physics, Chemistry, Biology, Mathematics
			- The Brain (Substrate): Electro physics, Biochemistry, Neuroanatomy, Neurophysiology
			- The Methods: Theoretical Physics (for example: diff. eq.), general computer science
			- The World (Problems:) Cognitive Science (Psychology, Psychophysics), Special Computer Science (Computer Vision, Robotics)
			- The Applications: Artificial Neural Networks, Chip Design
		- Different Approaches towards Brain and Behavior
		  collapsed:: true
			- Neuroscience:
				- Present Stimulus from an environment (e.g. light) to the neural system (e.g. anesthetized animals)
				- Behavior Response (e.g. change to heart, respiration, blood pressure or observable action in a psychophysical study)
			- Psychophysics (human behavioral studies):
				- Black Box translates Environment Stimulus into a Behavior Reaction
			- Neurophysiology (subfield of neurosciences):
				- Give Environment Stimulus (e.g. light) to anesthetized or moving animal
				- Use microelectrodes to recode the response in the brain of *one* neurons (e.g. in the visual cortex)
			- Theoretical/Computation Neuroscience
				- Treat brain as a computational system: Use math
				- Needs results from behavioral or neurophysiological experiments to fall back on
				- E.g. some AI-System has nothing to do with brain functions => Might not describe the brain
		- Levels of information processing in the nervous system:
		  collapsed:: true
			- Need to restrict your self to a small number of levels to gain understanding of a system
				- Models as a module, which allows the creation of new model for higher levels
				- Example: 20 neurons - Levels: Synapses, Neuros, Local Networks
				- “The best material model of a cat is another, or preferably the same, cat.” ― **Norbert Wiener**
			- Power of tens: Brain Levels
			  collapsed:: true
				- CNS (1 m)
				- Sub-Systems (10 cm)
				- Areas/"Maps" (1 cm)
				- Neurons (100 micrometer)
				- Local Networks (1mm)
				- Synapses (1 micrometer)
					- Cannot Simulate (hundreds of billions in the whole brain, Milliarde=billion )
				- Molecules (0.1 micrometer)
				  collapsed:: true
					- Cannot Simulate
		- Central Nervous System (CNS)
		  collapsed:: true
			- Describe big structures in the brain (anatomical similarities of structures => make out regions e.g. the cortex)
			- Site Note: Brains developed for one purpose to move.
				- Famous for F's (all about movement) : Fighting, Fleeing, Feeding, Mating
					- in worms mostly reflexive
				- A bigger body often corresponds to bigger body (more muscles)
			- Cortex:
			  collapsed:: true
				- Division into lobes
					- Frontal lobe - Emotional Process, Planning
					- Temporal lobe - auditory processing
					- occipital lobe, striate cortex - visual processing
					-
			- Where are things happening in the brain
			  collapsed:: true
				- Is the information represented locally?
					- Phrenologists view at the brain (18-19th century), shape of the scull to character,
					- Egyptians: People, who survive an arrow shot in the brain, go blind => Visual processing in back of the brain
					- Electrically Stimulation: Stimulate parts of the motor process => Leg Movement, Arm Movement
					- Maps in the brain for senses: Results from imaging techniques (Magnetic resonance imaging)
						- In the visual cortex: V4 response [almost only] to colorful stimulus, V5 [almost only] response mostly to motion
						- Sensual modality of one sense: Aspects are represented differently in the brain
					-
		- Systems
		  collapsed:: true
			- Visual System of a macaque monkey as more than 40 areas
			  collapsed:: true
				- parallel processing of "pixels"and image parts
				- hierarchical analysis of increasingly complex information
				- many lateral and feedback connectors
				- Retinal ganglion cells (RGC)
				- thalamus: Lateral geniculate nucleus (LGN)
				- Cortex: V1, V2, MT, etc.
				- Which areas are connected to which area and how strongly are they connected?
		- Area (Example: Primary Visual Cortex (V1)
			- Fibers
			  collapsed:: true
				- from Eye to optical chiasm: Optical nerve
				- from Optical chiasm to LGN: Optical tract
				- from LGN to Primary Visual Cortex: Optical radiations
			- Retinotopic Maps in V1:
			  collapsed:: true
				- V1 contains a retinotopic map of the visual Field. Adjacent Neurons represent adjacent regions in the retina. That particular small retinal region from which a single neuron receives its input is called the receptive field of this neuron.
				- V1 receives information from both eyes. Alternating regions in V1 (Ocular Dominanz Columns) receive (predominantely) Input from either the left or the right eye.
				- Each location in the cortex represents a different part of the visual scene through the activity of many neurons. Different neurons encode different aspects of the image. For example, *orientation of edges, color, motion speed and direction*, etc.
				- V1 decomposes an image into these components
			- Orientation selectivity in V1:
				- Brain does not react very much to uniformly illuminates surfaces. It reacts to contrasts (e.g. for edge detection)
				- David H. Hubel, Torsten N. Wiesel won Noble Price for their discoveries concerning information processing in the visual system [during the  60s]
					- In Cats neuros response to different orientation or movement of a light stimulus (an edge)
					- Orientation selective neurons in V1 change their activity (i.e., their frequency for generating action potentials) depending on the orientation of a light bar projected onto the receptive Field. These Neurons, thus, represent the orientation of lines oder edges in the image
					- Why is it important? Edge processing creates an image that can be recognized by you. Modern Computer Visions Algorithms make use of this. *See absolute classical book from: David Marr, 1982, Vision*
			- Complexity: What do I want to model? (E.g. sensitivity to an orientation)
			- What does a receptive field looks like?
				-
					- keep in mind V1 takes input from thalamus, nevertheless get information from retina
				- On-/Off = Contrast relative to background
				- can be generalized to any neuron in the brain
			- Superpositioning of maps in V1:
				- Thus, neurons in V1 are *orientation selective*. They are, however, also selective for *retinal position* and *ocular dominance* as well as for
				  *color* and *motion*. These are called **„features“**. The neurons are therefore akin to *„feature-detectors“*.
				- For each of these parameter there exists a **topographic map**.
				- These maps *co-exist* and *are superimposed* onto each other. In this way at every location in the cortex one finds a neuron which encodes a certain „feature“. This principle is called **„full coverage“**.
				- Add to image: Pixel concept of the brain:
					- column = Pillar on LR/Orientation plane
					- Rendering in visual cortex: Eye L/R, Stimulus Orientation (colors in image), the cortex has six layers.
					- while blob column = response to some color (e.g. red or yellow)
				-
		- Local Net (Orientation Selectivity)
		  collapsed:: true
			- Considerations for a Cortex Model (E.g. Small part of Visual Cortex)
			  collapsed:: true
				- Input
					- Structure of the visual pathway
				- Anatomy of the Cortex
					- Cell Types
					- Connections
				- Topography of the Cortex (Maps)
					- „X-Y Pixel-Space“ and its distortion
					- Ocularity-Map
					- Orientation-Map
					- Color
				- Functional Connectivity of the cortex
					- Connection Weights
					- Physiological charateristics of the neurons
				- At least all these things need to be considered when making a „complete“ cortex model
			- Done via projections onto cortical neuons
			  collapsed:: true
				- Image:
					- 9 retinal cells (have their own substructure: *center surround*; light response in the light in the center, weaker dark response surrounds the center), would be in reality not 3 in a row but more like 60-70 neurons
					- Convergence onto a conical simple cell for orientation selectivity (in V1)
			- Layers in the Cortex: V1-V6
			- Local Circuits in V1:
			  collapsed:: true
				- Many cell types:
					- Spiny stellate cell (dornentragende Sternzelle), pyramide cell (Pyramidenzellen), smooth stellate cell (dornenlose Sternzelle)
					- ${1mm}^3$ you have 3 kilometers of fibers in the cortex
					-
		- Neurons
			- Structure of a neuron (image pyramidal neuron)
				- At the **dendrite** the incoming signals arrive (incoming currents)
				- At the **soma** current are finally integrated.
				- At the **axon hillock** action potential are generated if the potential crosses the membrane threshold
				- The **axon** transmits (transports) the action potential to distant sites
					- blue stuff is Schwann cells act as a insulator around the axon, has a fatty lipid which heavily insulates, helps transmission speed and current lose
				- At the **synapses** are the outgoing signals transmitted onto the dendrites of the target neurons [or muscles]
			- Different Types of Neurons
				- Polarity
					- Unipolar cell (e.g. Invertebrate Neuron)
					- Bipolar cell (e.g. Retinal Bipolar cell)
					- Different Types of Multipolar cells
						- Spinal motoneuron
						- Hippocampal pyramidal cell
						- Purkinje cell of the cerebellum
			- Cell membrane:
				- Inside Cells
					- A- Negative charged proteins (Amino Acids)
					- K+ Potassium (Kalium)
				- Outside of the cell: salty liquid
					- Na+ Sodium (Nadium)
					- Cl- Chloid
			- Ion channels:
				- Channel Proteins:
				- Electrical Equilibrium for complete set of ions (Na+, Cl-, A-, K+)
				- Imbalance of individual ion concentrations (too much A- inside and to much Na+ outside) => builds up potential
			- Membrane Circuit diagram:
				- Caused by Imbalance of individual ion concentrations
				- $1/R=g$ conductance
				- the capacitor corresponds to the lipid bi-membrane (oil)
				- negative pol = inside of a neuron, positive pol outside of the neuron
				- $V_m=70 \ mV$
- # The tough stuff
	- ## Membrane Models
	  collapsed:: true
		- Neurophysiological Background - "The Neuron"
		  collapsed:: true
			- Structure
				- see above
			- Ion Channels
			  collapsed:: true
				- Two components of a nerve cell membrane
					- membrane proper: lipid bi layer
					- channels: made from protines, allow ions to pass through it, have two states: Open or Close, may permanently be open, limited to one type of ion
		- Electrical Membrane Properties & Ion channels
		  collapsed:: true
			- Membrane potential:
				- What does a neuron need to fire?
				  collapsed:: true
					- Depends on a few ions:
					  collapsed:: true
						- Potassium (K+)
						- Sodium (Na+)
						- Chloride (Cl-)
						- Calcium (Ca++)
							- important for synaptic transmissions
						- Protein Anions (A-)
					- For what types of ions is the membrane impermeable?
					  collapsed:: true
						- large protein anions A-
						- for sodium ions (at rest)
					- What is the consequence of this impermeablety?
					  collapsed:: true
						- Concentration difference and Potential difference emerge
						- video: Gibbs-donna equilibrium
				- Nernst equation
				  collapsed:: true
					- describes the equilibrium potential that arrives from the imbalance from any ion imbalance
					- $$V_x = - \frac{FT}{zF}\ln\frac{[X]_i}{[X]_o}$$
						- z = ion charge number: z(K+) = 1; z(Ca++) = 2
						- $[X]_o$ = concertation outside the cell
					- Simulation video
						- How do the concentrations and the temperature affect the equilibrium potential?
					- Does the Nernst Equation really capture the behavior of the membrane potential?
						- life is more complicated
						- experiment with step function -> other ions play a role when potassium drops to zero
				- Goldman-Hodgkin-Katz equation:
				  collapsed:: true
					- $$V_m=\frac{RT}{F} \ln \frac{ P_{K}[K^+]_o +  P_{Na}[Na^+]_o+P_{Cl}[Cl^-]_i}{ P_{K}[K^+]_i +  P_{Na}[Na^+]_i+P_{Cl}[Cl^-]_o}$$
					- Relies on the situation on: other ions: Cl- and Na+ (can not easily pass through membrane). When K is removed outside of the cell the other ions begin to play a role => Extension of Nernst equation with permeability coefficients $P_K$, $P_{Na}$, $P_{Cl}$
				- Potential of a Neuron at rest
				  collapsed:: true
					- Gibbs-Donnan Equilibrium
					- The Nernst Equation (for Potassium)
					- Contribution of more than one ion-type
				- Electrotonic process
				  collapsed:: true
					- Def. Potential change without Action Potential Generation
					- What can these electric changes do if you induce them (e.g. change potential of a neuron by inserting current with a electrode)?
					- Electrotonic Signal Propagation:
					  collapsed:: true
						- Inside the cell
							- Injected current flows out from the cell evenly across the membrane.
							- The cell membrane has everywhere the same potential after some time.
							- The change in membrane potention follows an exponential with time constant $\tau = RC$
								- Membrane Circuit diagram. (Channels = Resistor, Lipid bilayer = capacitor)
						- along a dendrite/axon
							- The potential decays along a dendrite (or axon) according to the distance from the current injection site.
							- At every location the temporal response follows an exponential but with ever decreasing amplitude
							- If plotting only the maxima against the distance then you will get another exponential
							- Amplification through active processes & complex geometries => Different shape of the potentials in the dendrite and the soma of a motoneuron. (Kabelequations)
		- Actionpotential
		  collapsed:: true
			- Advanced Version of the membrane's circuit diagram:
				- Simple Version was not realistic, because channels can open and close => changing resistance
				- image
				- the whole things gets more complicated due to the fact that there are many different ion channels all of which havve their own characteristics depending on the momentarily existing state of the cell
				- the conductivity of a channel depends on the membrane potential and on the concentration difference between intro- and extracellular space (and sometimes also on other parameters)
			- Action potential in general
				- shape
				- peak = opening of sodium channels
				- undershoot = increased potassium conductance
				- Threshold = min. stimulus voltage to trigger an action potential (potentials in a neuron can add up)
			- The Action Potential
				- Hodgkin and Huxley Model (Nobel Prize, 1963 Squid Giant Axon)
					- General Mambrane Equations
						-
					- Introduce time-dependence so as to get an Action Potential modelled
						- $$C \frac{dV_m}{dt}= -g_{Na}f_1(t)(V_m-V_{Na}) -g_{K}f_2(t)(V_m-V_{K}) -g_{L}f_3(t)(V_m-V_{L})+I_{Inj}$$
						- $f_i$ are fitted by data
						- $$C \frac{dV_m}{dt}= -\overline g_{Na}m^3 h(V_m-V_{Na}) -\overline g_{K}fn^4(V_m-V_{K}) - \overline g_{L}f_3(t)(V_m-V_{L})+I_{Inj}$$
					- Observations about Current Injection:
						- has threshold
						- spikes Potential if threshold is reached
					- Background on the spike form
				- How to measure Membrane Currents
				- More than one Action Potential
				- Voltage clamp method
					- developed 1949 by Kenneth Cole
					- used in the 1950s by Alan Hodgkin and Andrew Huxley to measure ion current while maintaining specific membrane potentials
						- TTX (tetrodotoxin) blocks sodium channel => measure only the potassium current
						- TEA (tetraethylammonium) blocks potassium channel => measure negative sodium current
				- Sodium channel (patch clamp method)
					- gave strong evedence for ion channels
					- use micropipettes to suck on the membrane => you get a very tight electical seal between the glass and the membrane
					- they measured saw either one, two or three channels at one time. => shows quantal natures
					- Process
						- Membrane depolarization
						- Na+ channels open
						- Na+ enter through channels
				- Action Potential /Firing Latency:
					- a higher current reduces the time until an action potential is elicited
				- Function of the sodium channel (how does it open and closes again)
					- 1) Resting closed
					- 2) Activated open
					- 3) Inactive state (1ms) closed
					- called refactory
				- Action Potential / Refactory Period:
					- Longer current pulses will lead to more action potentials.
					- However, directly after an action potential the ion channels are in an inactive state and cannot open. In addition, the membrane potential is rather hyperpolarized. Thus, the next action potential can only occur after a "waiting period" during which the cell return to its normal state.
					- This "waiting period is called the refractory period
				- Action Potential / Firing Rate:
					- When injecting current for longer durations an increase in current strength will lead to an increase of the number of action potentials 
					  per time. Thus, the firing rate of the neuron increases.
					- The maximum firing rate is limited by the absolute refractory period. (ca. 1ms)
				- Varying firing properties
					- Influence of steady hyperpolarization
					- Rhythmic burst in the absence of synaptic inputs (depolarized state) -> bursting neuron (calsium spikes), exists in the thalamus
					- Influence of the neurotransmitter acetylcholine
				- Action Potential /Shapes
				  collapsed:: true
					- different form in squid giant axon, tat muscles, cat heart, (depense on type of different channels present and their numbers)
		- Action Potential Propagation
		  collapsed:: true
			- Propagation of an Action Potential:
				- Action potentials propagate without being diminished (active process)
				- All sites along a nerve fiber will be depolarized until the potential passes threshold.
				- As soon as this happens a new AP will be elicited at some distance to the old one.
				- Main current flow is across the fiber.
		- Synaptic Transmission
		  collapsed:: true
			- Synapses and Neurotransmitters
			- Chemical synapse:
				- Entities that make sure that signal are transmitted from the presynaptic neuron to post synaptic neuron
				- Action potential comes -> turns into a chemical signals -> on the other side the chemical signals is turned again in the electical signal
				- electrical puls triggers opening up of vesicles, which contain neurotransmitters
				- neurotransmitter receptors are channel molecules. The channel will open, ions flow, excititory postsynaptic potential changes leads again to an action potential on the postsynaptic neuron. There are excitatory (increases ability to trigger another puls) and inhabitory (decreases postsynaptic neurons from spiking) potentials exists .
				- Neurotransmitters
					- Def. Chemicals (amino acids, peptides, monoamines) that transmit, amplity and modulate signals between neuron and another cell
					- Caus either excitatory or inhibitory PSPs
					- Glutamate - excitatory transmitter
					- Gaba, glycine - inhibitory transmitter
				- Synaptic Transmission:
					- Synapses are used to transmit signals from the axon of a source to the dendrite of a target neuron.
					- There are electrical (rare) and chemical synapses (very common)
					- At an electrical synapse we have directe electrical coupling (e.g. heart muscle cells)
						- Problem bidirectional flow
					- At a chemical synapse a chemical substane (transmitter) is used to transport the signal. Unidirectional transport (there are very rare and specific exceptions.)
					- Electrical synapses operate bi-directional and are extremely fast, chem. syn. operate uni-directional and are slower.
					- Chemical synapses can be excitatory or inhibitory they can enhance or reduce the signal change their synaptic strenght (this is what happens during learning)
				- Structure of a chemical synapse (motor endplate)
				- What happens at a chemical synapse during signal transmission?
					- The pre-synaptic action potential depolarises the axon terminals and Ca2+ channels open.
					- Ca2+ enters the pre-synaptic cell by which the transmitter vesicles are forced to open and release the transmitter.
					- Thereby the concentration of transmitter increases in the synaptic cleft and transmitter diffuses to the postsynaptic membrane.
					- Transmitter sensitive channels at the postsyaptic membrane open. Na+ and Ca2+ enter, K+ leaves the cell. An excitatory postsynaptic current (EPSC) is thereby generated which leads to an excitatory postsynaptic potential (EPSP).
				- Neurotransmitters and their (main) Actions:
					- Acetylcholine
					  collapsed:: true
						- Channel-type: nicotin. Receptor
						- Ion-current Na+ and K+
						- Action: excitartory
					- Glutamate
					  collapsed:: true
						- Channel-type: AMPA/Kainate
						- Ion-current Na+ and K+
						- Action: excitatory
					- GABA
					  collapsed:: true
						- Channel-type: GABA_A Receptor
						- Ion-current Cl-
						- Action: inhibitory
					- Glycine
						- Channel-type: GABA_A Receptor
						- Ion-current Cl-
						- Action: inhibitory
					- Acetylcholine
						- Channel-type: muscarin. Rec.
						- Ion-current -
						- Action: metabotropic, Ca2+ Release
					- Glutamate
						- Channel-type: NMDA
						- Ion-current Na+, K+, Ca2+
						- Action: voltage dependent blocked at resting potential
				- Synaptic Plasticity
					- change of synaptic transmission strength
					- Mg2+ blocks NMDA receptor => increase of AMPA receptors => bind more glutamate & amplification of postsynaptic signal
					- more complicated -> see later and other lectures
	- ## Spiking Neuron Models
	- Neural codes
	- Spiking models:
		- Hodgkin Huxley Model (repetition)
		  collapsed:: true
			- equations discriptions
			- dynamics of m are fast
			- dynamics of h and n are similar
		- Reduction of the HH-Model to two dimensions (general)
		  collapsed:: true
			- Introduction to dynamical systems
			  collapsed:: true
				- Example: Harmonic Oscillator
				- Phasediagram
				- Fixpoints
				- Nullclines
				- Limit cycles
			- General Reduction of the Hodgkin-Huxley Model: 2 dimensional Neuron Models
				- Assumptions that lead to the FH-Model
					- dm/dt = 0, h = const
				- $$\tau \frac{du}{dt}=F(u,w)+I(t)$$
				- $$\tau \frac{dw}{dt}=G(u,w)$$
		- Fitz Hugh-Nagumo Model
		  collapsed:: true
			- equations
				- $$\frac{du}{dt}=u-\frac{u^3}{3}-w+I$$
				- $$\frac{dw}{dt}=\epsilon(u+\beta+\gamma w)$$
				- u: membrane potential, w: recovery variable, I: stimulus
			- Analysis
			  collapsed:: true
				- look at nullclines
					- stable and unstable fixpoints
					- first order analysis
					- better approximation yield limit cycles and not diverging cycles!
				- limit cycle represent spiking
				- identify area for passive repolarization with no spikes and for spikes
				- no well-defined firing threshold
				- weak stimuli result in small trajectories (“subthreshold response”)
				- strong stimuli result in large trajectories (“suprathreshold response”)
				- BUT: it is only a quasi-thresholdalong the unstable middle branch of the V-nullcline
			- Physiological phenomena of the quasi threshold, captured by the FH-N Model
				- 1.Anodal break excitation If you hyper polarize a neuron and then quickly return to Vrest then a spike is elicited.
				- 2.Absolute and relative refractoriness: If your neuron has spiked it will not at all (abs.) or only with much input current(rel.) spike again.
				- 3.Periodic spiking followed by Excit. Block If you stimulate with fast increasing current, periodic spikes will be elicited but when the current gets too big spiking will stop.
				- 4.Spike accommodation If you stimulate with a too-slowly increasing current no spikeswill be elicited.
		- Integrate and Fire Model
			- two key aspects of neuronal excitability:
				- passive integrating response for small inputs
				- stereotype impulse, once the input exceeds a particular amplitude
			- equations and circuit
			- behavior when resting and when producing an input current
			- Non-linear E.g. quadratic I%F Model, exponential I&F model
				- difference how these system return to their fixpoint when there is no spike
	- ## Calculating with Neurons I: adding, subtracting, multiplying, dividing
	- ## Calculating with Neurons II: Integration, differentiation
	- ## Calculating with Neurons III: networks, vector-/matrix- calculus, assoc. memory
	- ## Information processing in the cortex I: Neurons as filters
	- ## Information processing in the cortex II:Correlation analysis of neuronal connections
	- ## Information processing in the cortex III: Neural Codes and population responses
	- ## Information processing in the cortex IV: Neuronal maps
- # Something interesting - the broader perspective
  collapsed:: true
	- ## On Intelligence and Cognition – Computational Properties?
- # Motor Function
  collapsed:: true
	- ## Models of Motor Control
- # Adaptive Mechanisms
  collapsed:: true
	- Learning and plasticity I: Physiological mechanisms and formal learning rules
	- Learning and plasticity II: Developmental models of neuronal maps
	- Learning and plasticity III: Sequence learning, conditioningHigher functions
- ## Higher functions
  collapsed:: true
	- Memory: Models of the Hippocampus
	- Models of Attention, Sleep and Cognitive Processes