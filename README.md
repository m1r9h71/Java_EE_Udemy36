# Java_EE_Udemy36
Reading the list of available flights
In FlightService:

     public List<Flight> getFlights() {
    	
    	TypedQuery<Flight> query = em.createQuery("SELECT f FROM Flight f", Flight.class);
    	
    	List<Flight> results = query.getResultList();
    	
    	return results;
    	
    }
    
In Flights (new Servlet)inside doGet:

    List<Flight> fList = (List<Flight>) fs.getFlights();
		
		request.setAttribute("flight_list", fList);
		
		PrintWriter out = response.getWriter();
		
		out.println("List of Flights will be displayed here: ");
