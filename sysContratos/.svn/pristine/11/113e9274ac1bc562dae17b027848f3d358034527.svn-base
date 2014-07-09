package cl.ips.gob.sysContratos.managedBean;

import java.io.Serializable;

import javax.faces.application.FacesMessage;
import javax.faces.bean.ManagedBean;
import javax.faces.bean.SessionScoped;
import javax.faces.context.FacesContext;
import javax.servlet.http.HttpSession;

import org.jboss.logging.Logger;

import cl.ips.gob.sysContratos.util.ServletUtil;

@ManagedBean(name = "loginBean")
@SessionScoped
public class LoginBean implements Serializable {

	/**
	 * 
	 */
	private static final long serialVersionUID = 1L;

	private static final Logger logger = Logger.getLogger(LoginBean.class);

	private String username;
	private String password;

	public LoginBean() {
		this.username = "";
		this.password = "";
	}

	public String getUsername() {
		return username;
	}

	public void setUsername(String username) {
		this.username = username;
	}

	public String getPassword() {
		return password;
	}

	public void setPassword(String password) {
		this.password = password;
	}

	public String validaLoginAction() {
		logger.info("entrando al botón");
		if (this.username != null && this.password != null
				&& !this.username.trim().equals("")
				&& !this.password.trim().equals("")
				&& this.username.trim().equals("psep")
				&& this.password.trim().equals("123456")) {
			HttpSession session = ServletUtil.getSession();
			session.setAttribute("username", this.username);

			return "index?faces-redirect=true";
		} else {
			FacesContext.getCurrentInstance().addMessage(
					null,
					new FacesMessage(FacesMessage.SEVERITY_ERROR, "Error",
							"Error en usuario y/o password"));
			return null;
		}
	}

	public String logoutAction() {
		HttpSession session = ServletUtil.getSession();
		session.invalidate();
		return "login?faces-redirect=true";
	}

}
