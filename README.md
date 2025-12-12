

we deploy the AnyLogic Event (Event Triggering sales) block, where the java function performs the desired condition to get stock information from DES. Then using this stock information (obtained from Step-1), we incorporate dynamic variables and parameters that influence the demand and marketing strategy of a new product development. For analyzing the behavior of these variables, we apply the Bass diffusion model (Santa-Eulalia et al. 2011) into this SD simulation using the Equation (1) for getting the information on the coefficient of innovation & imitation in our model:

	\frac{dN\left(t\right)}{dt}=p\cdot\left(M-N\left(t\right)\right)+q\cdot\frac{N\left(t\right)}{M}\cdot\left(M-N\left(t\right)\right)           	(1)

	
Where N(t) is cumulative number of adopters at time t, M is the total potential market size (number of potential adopters), p is the coefficient of innovation (probability of adoption due to external influence like advertising), q is coefficient of imitation, in other words, the probability of adoption due to the word of mouth (WOM) effect. In this section, SD captures the aggregate demand dynamics by modeling the transition of potential users to adopted users, driven by innovation (external influence) and imitation (WOM effects). In a market, WOM serves as a powerful form of informal communication, providing a competitive advantage. The integration occurs through event triggers, where changes in demand from the SD model initiate purchase events in DES, and real-time feedback from DES updates the SD parameters, ensuring dynamic system behavior. Based on the dynamic variable (Advertising effect, WOM), this model calculates purchase decisions that are added to the market demand. The adopted user (who already purchased the products) gives replacement decisions based on product lifetime, which is also a significant factor that updates the demand. This hybrid approach enables businesses, particularly in the edible oil industry, to better anticipate market fluctuations, optimize production and inventory levels, and improve decision-making by combining the predictive power of SD with the granular insights of DES. 


Input: Cnrate, cnefect, AdEffect, credibility (Parameters)
Output: Customer Demand Quantity Based on the value of Promotional Strategy.
Initialization: CDemand Rate, PotentialUsers   for the Day Dl where l=1,2,3…. Product Lifetime (days); The promotional effects change rate Cijk where ijk represents the variation in effect measurements based on observed managerial insights. conditionExecuted as true and conditionStartDay = 1; 
	for (int day=Dl; day <DPLT; D++) {// PLT is Product Lifetime.
	If (CDemand<=n & PotentialUsers   <=m) {// n,m minimum rate considered by authority
	for (month=1; month <12; month ++) {//Since Product lifetime 1 year
	Update the value of Cnrate, cnefect, AdEffect, credibility
	Updating the values =(random.nextDouble() * 2-1) *Cijk * Parameters;// Updating the values based on condition.
	                 }// Closing first condition
             } // Closing second condition
	          };// Closing third condition
	If (! conditionExecuted) {// When demand falls below certain amount
	Initialization: conditionStartDay = day;
	               }; End of the loop
	 if (conditionExecuted && day - conditionStartDay <=D) {
	PotentialUsers = x;//x is the value to update as required
	else if (conditionExecuted && day - conditionStartDay >= D) {
	PotentialUsers -= P; /P-the value user can update as required.
	PotentialUsers = Math.max (100, PotentialUsers);// minimum threshold.        
	          }
	     };
	End
