package cl.ips.gob.sysContratos.managedBean;

import javax.faces.bean.ManagedBean;
import javax.faces.bean.RequestScoped;

import org.jboss.logging.Logger;
//import javax.faces.bean.SessionScoped;

@ManagedBean(name="testBean")
@RequestScoped
public class TestBean {
	
	private static final Logger logger = Logger.getLogger(TestBean.class);
	
	private String message;
	
	public TestBean() {
		this.message = "Output de prueba";
	}

	public String getMessage() {
		return message;
	}

	public void setMessage(String message) {
		this.message = message;
	}
	
	public void saludaAction() {
		logger.info("hiciste click en el botón");
		this.message = "Hola!!!!";
	}
	
	public String redirectPagina2Action() {
		return "page2?faces-redirect=true";
	}

}
