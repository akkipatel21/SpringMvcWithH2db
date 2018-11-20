# SpringMvcWithH2db

> In this tutorial you will know how to create Spring boot 1.5.3 MVC  example in simplest way.
### Project Structure

![](extra/projectStructure.png)


#### Step 1 - Let’s Setup Environment

1. Spring 1.5.16.BUILD-SNAPSHOT and any latest version
2. Maven 3 and any latest version
3. JDK 1.6 / JDK 1.7 / JDK 1.8 / JDK 1.9
4. Eclipse Kepler / Eclipse Juno / Eclipse Neon
5. Tomcat 6 / Tomcat 7 / Tomcat 8 / Tomcat 9


#### Step 2 - Add Dipendency in ``pom.xml`` file

```XML
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.spring</groupId>
	<artifactId>controller</artifactId>
	<name>SpringWithHibernateCrud123</name>
	<packaging>war</packaging>
	<version>1.0.0-BUILD-SNAPSHOT</version>
	<properties>
		<java-version>1.8</java-version>
		<org.springframework-version>4.1.6.RELEASE</org.springframework-version>
		 <hibernate.version>4.3.10.Final</hibernate.version>
        <mysql.connector.version>5.1.31</mysql.connector.version>
		<org.aspectj-version>1.6.10</org.aspectj-version>
		<org.slf4j-version>1.6.6</org.slf4j-version>
	</properties>
	<dependencies>
		<!-- Spring -->
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
			<version>${org.springframework-version}</version>
			<exclusions>
				<!-- Exclude Commons Logging in favor of SLF4j -->
				<exclusion>
					<groupId>commons-logging</groupId>
					<artifactId>commons-logging</artifactId>
				 </exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-webmvc</artifactId>
			<version>${org.springframework-version}</version>
		</dependency>
				
		<!-- AspectJ -->
		<dependency>
			<groupId>org.aspectj</groupId>
			<artifactId>aspectjrt</artifactId>
			<version>${org.aspectj-version}</version>
		</dependency>
		<dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
            <version>${org.springframework-version}</version>
        </dependency>
        <dependency>
            <groupId>com.h2database</groupId>
            <artifactId>h2</artifactId>
            <version>1.4.192</version>
        </dependency>
		<!-- Hibernate -->
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-core</artifactId>
            <version>${hibernate.version}</version>
        </dependency>
        		<!--jeckson  -->
		 <dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-core</artifactId>
			<version>2.2.3</version>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-databind</artifactId>
			<version>2.2.3</version>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-annotations</artifactId>
			<version>2.2.3</version>
		</dependency>
			    
			<dependency>
			    <groupId>org.codehaus.jackson</groupId>
			    <artifactId>jackson-core-asl</artifactId>
			    <version>1.9.13</version>
			</dependency>
			
			<dependency>
			    <groupId>org.codehaus.jackson</groupId>
			    <artifactId>jackson-mapper-asl</artifactId>
			    <version>1.9.13</version>
			</dependency>
        <!--orm  -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-orm</artifactId>
            <version>${org.springframework-version}</version>
        </dependency>
		
		<!-- Logging -->
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-api</artifactId>
			<version>${org.slf4j-version}</version>
		</dependency>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>jcl-over-slf4j</artifactId>
			<version>${org.slf4j-version}</version>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-log4j12</artifactId>
			<version>${org.slf4j-version}</version>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>log4j</groupId>
			<artifactId>log4j</artifactId>
			<version>1.2.15</version>
			<exclusions>
				<exclusion>
					<groupId>javax.mail</groupId>
					<artifactId>mail</artifactId>
				</exclusion>
				<exclusion>
					<groupId>javax.jms</groupId>
					<artifactId>jms</artifactId>
				</exclusion>
				<exclusion>
					<groupId>com.sun.jdmk</groupId>
					<artifactId>jmxtools</artifactId>
				</exclusion>
				<exclusion>
					<groupId>com.sun.jmx</groupId>
					<artifactId>jmxri</artifactId>
				</exclusion>
			</exclusions>
			<scope>runtime</scope>
		</dependency>

		<!-- @Inject -->
		<dependency>
			<groupId>javax.inject</groupId>
			<artifactId>javax.inject</artifactId>
			<version>1</version>
		</dependency>
				
		<!-- Servlet -->
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>servlet-api</artifactId>
			<version>2.5</version>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>javax.servlet.jsp</groupId>
			<artifactId>jsp-api</artifactId>
			<version>2.1</version>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>jstl</artifactId>
			<version>1.2</version>
		</dependency>
		 <!-- jsr303 validation -->
        <dependency>
            <groupId>javax.validation</groupId>
            <artifactId>validation-api</artifactId>
            <version>1.1.0.Final</version>
        </dependency>
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-validator</artifactId>
            <version>5.1.3.Final</version>
        </dependency>
 
        <!-- MySQL -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>${mysql.connector.version}</version>
        </dependency>
	
		<!-- Test -->
		<dependency>
			<groupId>junit</groupId>
			<artifactId>junit</artifactId>
			<version>4.7</version>
			<scope>test</scope>
		</dependency>        
	</dependencies>
    <build>
        <plugins>
            <plugin>
                <artifactId>maven-eclipse-plugin</artifactId>
                <version>2.9</version>
                <configuration>
                    <additionalProjectnatures>
                        <projectnature>org.springframework.ide.eclipse.core.springnature</projectnature>
                    </additionalProjectnatures>
                    <additionalBuildcommands>
                        <buildcommand>org.springframework.ide.eclipse.core.springbuilder</buildcommand>
                    </additionalBuildcommands>
                    <downloadSources>true</downloadSources>
                    <downloadJavadocs>true</downloadJavadocs>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>2.5.1</version>
                <configuration>
                    <source>1.6</source>
                    <target>1.6</target>
                    <compilerArgument>-Xlint:all</compilerArgument>
                    <showWarnings>true</showWarnings>
                    <showDeprecation>true</showDeprecation>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>exec-maven-plugin</artifactId>
                <version>1.2.1</version>
                <configuration>
                    <mainClass>org.test.int1.Main</mainClass>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>


```


#### Step 3 - Add all package to above structure
first i add com.spring.configuration.
```JAVA
package com.spring.configuration;

import java.sql.SQLException;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

@Configuration
@ComponentScan
public class JavaConfiguration {
 //... other beans
  
 @Bean(initMethod="start",destroyMethod="stop")
 public org.h2.tools.Server h2WebConsonleServer () throws SQLException {
   return org.h2.tools.Server.createWebServer("-web","-webAllowOthers","-webDaemon","-webPort", "8084");
 }
}


<!-- End Here -->
```

And second one is controller
```JAVA
package com.spring.controller;

import java.lang.reflect.Method;
import java.lang.reflect.Parameter;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.text.DateFormat;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;
import java.util.Locale;
import java.util.function.Predicate;
import java.util.stream.Collectors;

import javax.transaction.HeuristicMixedException;
import javax.transaction.HeuristicRollbackException;
import javax.transaction.RollbackException;
import javax.transaction.SystemException;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.PropertySource;
import org.springframework.context.support.PropertySourcesPlaceholderConfigurer;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.ResponseBody;

import com.spring.dao.EmployeeDao;
import com.spring.model.Employee;

/**
 * Handles requests for the application home page.
 */
@Controller
/*@Configuration
@ComponentScan(basePackages="com.spring")
@PropertySource(value ={"classpath:database.properties"})*/
public class MainController {
	
	private static final Logger logger = LoggerFactory.getLogger(MainController.class);
	
	@Autowired
	EmployeeDao empDao;
	/*@RequestMapping(value = "/", method = RequestMethod.GET)
	public String home(Locale locale, Model model) {
		logger.info("Welcome home! The client locale is {}.", locale);
		return "emp1";
	}*/
	
	@RequestMapping(value = "/", method = RequestMethod.GET)
	public String home(Locale locale, Model model) {
		logger.info("Welcome home! The client locale is {}.", locale);
		return "emp";
	}
	@RequestMapping(value = "insertInfo", method = RequestMethod.POST,produces="application/json")
	@ResponseBody
	public int insertData(@RequestParam("fname")String firstname,
			@RequestParam("lname")String lastname,
			@RequestParam("address")String address,
			@RequestParam("gen") String gen, Model model) throws  RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException {
		logger.info("Welcome insertData()");
		logger.info("fname"+firstname);
		logger.info("fname"+lastname);
		logger.info("fname"+address);
		logger.info("gen"+gen);
		
		Employee empBean= new Employee();
		empBean.setFirstname(firstname);
		empBean.setLastname(lastname);
		empBean.setAddress(address);
		empBean.setDflag(1);
		empBean.setGender(gen);
		
		int i = empDao.addEmployee(empBean);
		logger.info("Welcome insertData()"+empBean);
		if(i>0){
			i = 1;
		}else{
			i = 0;
		}
		return i;
	}
	@RequestMapping(value = "showAll", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public ArrayList<Employee> showAll(Locale locale, Model model) {
		logger.info("Welcome ShowData()");
		//model.addAttribute("show", empDao.listemployee());
		ArrayList<Employee> emplist = empDao.listemployee();
		for (Employee temp : empDao.listemployee()) {
			System.out.println(temp);
		}
		return emplist;
	}
	
	@RequestMapping(value = "searchName", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public List<Employee> searchName(@RequestParam("firstname")String search, Model model) throws ClassNotFoundException {
		logger.info("Welcome searchName()");
		logger.info("search :: "+search);
		//model.addAttribute("show", empDao.listemployee());
		ArrayList<Employee> emplist = empDao.listemployee();
		Predicate<Employee> p1 = e -> e.getFirstname().equalsIgnoreCase(search)  && e.getDflag() == 1;
		Employee newemp = new Employee(); 
		Class cls = newemp.getClass();
		 //Class cls = Class.forName("p1");
	        // Getting declared methods inside the Calculate class  
	        Method[] method = cls.getDeclaredMethods(); // It returns array of methods  
	        // Iterating method array  
	        for (Method method2 : method) {  
	            System.out.println(method2.getName().toString());    // getting name of method  
	            // Getting parameters of each method  
	            Parameter parameter[] = method2.getParameters(); // It returns array of parameters  
	            // Iterating parameter array  
	            for (Parameter parameter2 : parameter) {  
	                System.out.println(""+parameter2.getParameterizedType().toString()); // returns type of parameter  
	                System.out.println(""+parameter2.getName().toString()); // returns parameter name  
	            }   
	        }  
		boolean b1 = emplist.stream().anyMatch(p1);
	     System.out.println(b1);
		//List<String>  val1 =emplist.stream().filter(e->e.getFirstname() == search).map(e->e.getFirstname()).collect(Collectors.toList());
		List<Employee>  val1 =(List<Employee>) emplist.stream().parallel().filter(e->e.getFirstname().equalsIgnoreCase(search) && e.getDflag() ==1).sequential().collect(Collectors.toList());
       // Long  val2 =plist.stream().filter(p->p.name == "pratik").map(p->p.name).collect(Collectors.counting());
        System.out.println("val1 ::"+val1);
       //System.out.println("val2 ::"+val2);
		return val1;
	}
	/*@RequestMapping(value = "findEmp", method = RequestMethod.GET)
	public String findEmp(@RequestParam("skill")String[] skill, Model model) {
		for (int i = 0; i < skill.length; i++) {
			logger.info("skill is"+skill[i]);
		}
		
		model.addAttribute("editemp", empDao.findBySkill(skill));
		return "employeelist";
	}*/
	@RequestMapping(value = "editData", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public Employee editEmployee(@RequestParam("id")int id, Model model) {
		logger.info("id is"+id);
		//model.addAttribute("editemp", empDao.getById(id));
		Employee em = empDao.getById(id);
		return em;
	}
	@RequestMapping(value = "deleteData", method = RequestMethod.POST ,produces="application/json")
	@ResponseBody
	public String deleteEmployee(@RequestParam("id")int id, Model model) throws SecurityException, RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException {
		logger.info("id is"+id);
		
		//int i  =empDao.deleteEmp(id);
		int i  =empDao.deleteEmpUsingMerge(id);
		String rtn = "";
		if(i>0){
			rtn = "1";
		}else{
			rtn ="0";
		}
		return rtn;
	}
	@RequestMapping(value = "updateInfo", method = RequestMethod.POST ,produces="application/json")
	@ResponseBody
	public int updateEmployee(@RequestParam("id")int id,
			@RequestParam("fname")String firstname,
			@RequestParam("lname")String lastname,
			@RequestParam("gen")String gen,
			@RequestParam("address")String address, Model model) throws  RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException {
		logger.info("id is"+id);
		logger.info("fname"+firstname);
		logger.info("lastname"+lastname);
		logger.info("gen"+gen);
		logger.info("address"+address);
		Employee empBean = new Employee();
		empBean.setId(id);
		empBean.setFirstname(firstname);
		empBean.setLastname(lastname);
		empBean.setAddress(address);
		empBean.setGender(gen);
		empBean.setDflag(1);
		empBean = empDao.updateEmployee(empBean);
		int i;
		 if(empBean.getId()>0){
			 return i = 1;
		 }else{
			 return i = 0;
		 }
		 
		//return i;
	}
	/*@RequestMapping(value = "serchAJAX", method = RequestMethod.GET , produces="application/json")
	@ResponseBody
	public ArrayList<Employee> serchAJAX( @RequestParam("skill") String[] skill)  {
		logger.info("serchajax()");
		for (int i = 0; i < skill.length; i++) {
			logger.info("skill is"+skill[i]);
		}
		
		
		Employee emp = null;
        //ArrayList<Employee> empFname = new ArrayList<Employee>();
        String skl =" "; 
        for (int i = 0; i < skill.length; i++) {
			skl = skl+skill[i]+"";
		}
        emp.setSkill(skl);
        ArrayList<Employee> empfname = empDao.findBySkill(emp);
        
		try {
			Class.forName("com.mysql.jdbc.Driver");
			con = DriverManager.getConnection("jdbc:mysql://localhost:3306/test", "root", "root");
			Statement st =con.createStatement();
			ResultSet rs = st.executeQuery("select * from emp where skill like '%"+skill+"%'; ");
			while( rs.next() ){
				ben = new EmployeeBen();
				ben.setFname(rs.getString("fname"));
				System.out.println(ben.getFname());
				empFname.add(ben);
			}
			 
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		return empfname;
	}*/
	 @Bean
	    public static PropertySourcesPlaceholderConfigurer propertySourcesPlaceholderConfigurer() {
	        return new PropertySourcesPlaceholderConfigurer();
	    }
	
}

<!-- End Here -->
```

```JAVA
package com.spring.dao;

import java.util.ArrayList;

import javax.annotation.Resource;
import javax.persistence.ValidationMode;
import javax.transaction.HeuristicMixedException;
import javax.transaction.HeuristicRollbackException;
import javax.transaction.RollbackException;
import javax.transaction.SystemException;


import javax.transaction.Transactional;

import org.hibernate.Query;
import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.Transaction;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

import com.spring.model.Employee;

@Component
/*@Resource
@Qualifier("empDao")
@Transactional()*/
public class EmployeeDao {
	
	@Autowired
	SessionFactory sessionFactory;

	/*public void setSessionFactory(SessionFactory sessionFactory) {
		this.sessionFactory = sessionFactory;
	}
	*/ @Transactional()
	public int addEmployee(Employee empBean) throws RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException{
		/*Session session= sessionFactory.getCurrentSession();*/
		Session session = sessionFactory.openSession();
		  Transaction tx = session.beginTransaction();
		/*Session session= sessionFactory.getCurrentSession();*/
	    int  i = (Integer) session.save(empBean);
		/*Session session = sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "INSERT INTO Employee(firstName, lastName, address) values(?,?,?)"  + 
	             "SELECT firstName, lastName,address FROM employee400";
		
		session.save(empBean.getFirstname());
		session.save(empBean.getLastname());
		session.save(empBean.get);
	Query query = session.createQuery(hql);
	query.setParameter(1, empBean.getLastname());
	query.setParameter(2, empBean.getLastname());
	query.setParameter(3, empBean.getAddress());
	int result = query.executeUpdate();
	System.out.println("Rows affected: " + result);*/
	    tx.commit();
	    session.close();
	    System.out.println("employee saved successfully, Person Details="+empBean);
	    System.out.println("emp id is "+i);
		return i;
		}
	 @Transactional()
	public Employee updateEmployee(Employee empBean) throws RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException{
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
	    Employee em = (Employee) session.merge(empBean);
	    tx.commit();
	    session.close();
	    System.out.println("Employee update successfully, Person Details="+empBean);
		return em;
		}
	 @Transactional()
	 @SuppressWarnings("unchecked")
	public ArrayList<Employee> listemployee(){
		ArrayList<Employee> empList = new ArrayList<Employee>();
		 /*for(Employee empBean : empList){
	            logger.info("Person List::"+p);
	        }*/
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "FROM Employee WHERE dflag = :dflag";
		Query query = session.createQuery(hql);
		query.setParameter("dflag",1);
		return (ArrayList<Employee>) query.list();
		/*return (ArrayList<Employee>) sessionFactory.openSession().createQuery("SELECT E.* FROM Employee E WHERE E.dflag =: 1 ")
			    .list();*/
		/*return (ArrayList<Employee>) sessionFactory.openSession().createQuery("select id, firstname , lastname , address from Employee where dflag = 1")
			    .list();*/
		}
	 @Transactional()
	public Employee getById(int id){
		return (Employee) sessionFactory.openSession().get(Employee.class, id);
		}
	 @Transactional()
	public Integer deleteEmp(int id) throws RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException{
		 System.out.println("before id :"+id +"dflag"+((Employee) sessionFactory.openSession().get(Employee.class, id)).getDflag());
	 	 /*Employee emp  = new Employee();
	 	 emp.setDflag(0);
	 	 emp.setId(id);*/
		 Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "Update Employee set dflag = :dflag where id = "+id;
		Query query = session.createQuery(hql);
		query.setParameter("dflag",0);
		int i = query.executeUpdate();
		System.out.println("i is :::"+i);
		/*session.createQuery("update Employee E set E.dfalg = 0 where E.id ="+id).executeUpdate();*/
		//String hql = "update Employee set dfalg = 1 where id ="+ id ;
	             
		//Query query = session.createQuery(hql);
		//query.executeUpdate();
		tx.commit();
		System.out.println("after id:"+id+" dflag = "+((Employee) sessionFactory.openSession().get(Employee.class, id)).getDflag());
		if(i>0){
			i = 1;
		}else{
			i=0;
		}
		  session.close();
		return i;
	}
	/* @Transactional()
	 @SuppressWarnings("unchecked")
	public ArrayList<Employee> findBySkill(Employee emp) {
		ArrayList<Employee> empList = new ArrayList<Employee>();
		 for(Employee empBean : empList){
	            logger.info("Person List::"+p);
	        }
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "FROM Employee WHERE skill = :skill";
		Query query = session.createQuery(hql);
		query.setParameter("skill",emp.getSkill());
		return (ArrayList<Employee>) query.list();
		
		
	}*/
	public int deleteEmpUsingMerge(int id) {
		System.out.println("before id :"+id +"dflag"+((Employee) sessionFactory.openSession().get(Employee.class, id)).getDflag());
	 	 /*Employee emp  = new Employee();
	 	 emp.setDflag(0);
	 	 emp.setId(id);*/
		Employee em = new Employee();
		Employee emp = getById(id);
		em.setFirstname(emp.getFirstname());
		em.setLastname(emp.getLastname());
		em.setId(emp.getId());
		em.setAddress(emp.getAddress());
		emp.setDflag(0);
		em.setGender(emp.getGender());
		//Employee emp = new Employee();
		
		 Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		//String hql = "Update Employee set dflag = :dflag where id = "+id;
		//Query query = session.createQuery(hql);
		emp = (Employee) session.merge(emp);
		//query.setParameter("dflag",0);
		//int i = query.executeUpdate();
		int  i = emp.getId();
		System.out.println("i is :::"+i);
		/*session.createQuery("update Employee E set E.dfalg = 0 where E.id ="+id).executeUpdate();*/
		//String hql = "update Employee set dfalg = 1 where id ="+ id ;
	             
		//Query query = session.createQuery(hql);
		//query.executeUpdate();
		tx.commit();
		System.out.println("after id:"+id+" dflag = "+((Employee) sessionFactory.openSession().get(Employee.class, id)).getDflag());
		if(i>0){
			i = 1;
		}else{
			i=0;
		}
		  session.close();
		return i;
	}

}

<!-- End Here -->
```
com.spring.model

```JAVA
package com.spring.model;

import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.InputStream;
import java.util.Date;
import java.util.Properties;

public class CrunchifyGetPropertyValues {
	String result = "";
	InputStream inputStream;
 
	public String getPropValues() throws IOException {
 
		try {
			Properties prop = new Properties();
			String propFileName = "database.properties";
 
			inputStream = getClass().getClassLoader().getResourceAsStream(propFileName);
 
			if (inputStream != null) {
				prop.load(inputStream);
			} else {
				throw new FileNotFoundException("property file '" + propFileName + "' not found in the classpath");
			}
 
			Date time = new Date(System.currentTimeMillis());
 
			// get the property value and print it out
			String driverClassName = prop.getProperty("driverClassName");
			String url = prop.getProperty("url");
			String username = prop.getProperty("username");
			String password = prop.getProperty("password");
			//String consolePath= prop.getProperty("spring.h2.console.path");
			
			result = "database path = " + driverClassName + ", " + url + ", " + username+","+ password;
			//result = "database path = " + driverClassName + ", " + url + ", " + username+","+ password + ","+consolePath;
			System.out.println(result + "\nProgram Ran on " + time);
		} catch (Exception e) {
			System.out.println("Exception: " + e);
		} finally {
			inputStream.close();
		}
		return result;
		
	}
}


<!-- End Here -->
```

```JAVA
package com.spring.model;

import java.io.IOException;

public class CrunchifyReadConfigMain {
	
	public static void main(String[] args) throws IOException {
		CrunchifyGetPropertyValues properties = new CrunchifyGetPropertyValues();
		properties.getPropValues();
	}
}


<!-- End Here -->
```

com.spring.model
```JAVA
package com.spring.model;

import java.io.Serializable;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.Table;
import javax.persistence.TableGenerator;
import javax.persistence.Transient;

@Entity
@Table(name="employeep")
public class Employee implements Serializable{
	
	@Id
	//@TableGenerator(name="TABLE_GEN",table="T_GENERATOR",pkColumnName="GEN_KEY",pkColumnValue="TEST",valueColumnName="GEN_VALUE",initialValue=1,allocationSize=1)
	//@GeneratedValue(strategy=GenerationType.TABLE, generator="TABLE_GEN")
	@GeneratedValue(strategy=GenerationType.AUTO)
	@Column(name="id")
	private int id;
	
	@Column(name="firstname")
	private String firstname;
	
	@Column(name ="lastname")
	private String lastname;
	
	@Column(name="address")
	private String address;
	
	/*@Column(name="skill")
	private String skill;*/
	@Column(name="gender")
	private String gender;
	
	//@Transient
	@Column(name="dflag")
	private int dflag;
	
	/*public Employee()*/
	
	/*public Employee(Employee e) {
		// TODO Auto-generated constructor stub
	}*/
	public int getDflag() {
		return dflag;
	}
	public void setDflag(int dflag) {
		this.dflag = dflag;
	}
	public int getId() {
		return id;
	}
	public void setId(int id) {
		this.id = id;
	}
	public String getFirstname() {
		return firstname;
	}
	public void setFirstname(String firstname) {
		this.firstname = firstname;
	}
	public String getLastname() {
		return lastname;
	}
	public void setLastname(String lastname) {
		this.lastname = lastname;
	}
	public String getAddress() {
		return address;
	}
	public void setAddress(String address) {
		this.address = address;
	}
	
	
	public String getGender() {
		return gender;
	}
	public void setGender(String gender) {
		this.gender = gender;
	}
	/*public String getSkill() {
		return skill;
	}
	public void setSkill(String skill) {
		this.skill = skill;
	}*/
	@Override
	public String toString() {
		return "Employee [id=" + id + ", firstname=" + firstname
				+ ", lastname=" + lastname + ", address=" + address
				+  ", dflag=" + dflag + "]";/*;, skill=" + skill +
*/	}
	
	

}

<!-- End Here -->
```
com.spring.model
```JAVA
package com.spring.model;

import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.util.Properties;

public class LoadProperty {
	

		Properties prop = new Properties();
		InputStream input = null;
		{

		try {

			input = new FileInputStream("config.properties");

			// load a properties file
			prop.load(input);

			// get the property value and print it out
			System.out.println(prop.getProperty("database"));
			System.out.println(prop.getProperty("dbuser"));
			System.out.println(prop.getProperty("dbpassword"));

		} catch (IOException ex) {
			ex.printStackTrace();
		} finally {
			if (input != null) {
				try {
					input.close();
				} catch (IOException e) {
					e.printStackTrace();
				}
			}
		}

	  }

}


<!-- End Here -->
```
src/main/resource

```database.properties
#driverClassName=com.mysql.jdbc.Driver
#url=jdbc\:mysql\://localhost\:3306/testdb
#username=root
#password=123456

driverClassName=org.h2.Driver
#url=jdbc:h2:file:~/h2/testdb1;DB_CLOSE_ON_EXIT=FALSE;AUTO_SERVER=TRUE
url=jdbc:h2:file:~/h2/testdb1
#DB_CLOSE_ON_EXIT=FALSE;AUTO_SERVER=TRUE
username=sa
password=
h2.console.path=/h2_console


<!-- End Here -->
```

#### Step 4 - Add appServlet configuration ``servlet-context.xml`` file

```XML
<?xml version="1.0" encoding="UTF-8"?>
<beans:beans xmlns="http://www.springframework.org/schema/mvc"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:beans="http://www.springframework.org/schema/beans"
	xmlns:context="http://www.springframework.org/schema/context"
	xsi:schemaLocation="http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc.xsd
		http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">

	<!-- DispatcherServlet Context: defines this servlet's request-processing infrastructure -->
	
	<!-- Enables the Spring MVC @Controller programming model -->
	<annotation-driven />
	<beans:bean id="propertyConfigurer" class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
	  <beans:property name="ignoreUnresolvablePlaceholders" value="true"/>
		<beans:property name="locations">
			<beans:list>
				<beans:value>classpath:database.properties</beans:value><!-- "src/main/webapp/WEB-INF/spring/appServlet/database.properties" -->
			</beans:list>
		</beans:property>
	</beans:bean>
	
	<!-- <tx:annotation-driven transaction-manager="hibernateTransactionManager"/> -->
	<beans:bean id="transactionManager" class="org.springframework.orm.hibernate4.HibernateTransactionManager" >
		<beans:property name="sessionFactory" ref="sessionFactory"></beans:property>
	</beans:bean>
	<!-- <tx:annotation-driven transaction-manager="transactionManager"/> -->

	<!-- <context:property-placeholder location="classpath:database.properties"/> -->
	<!-- </context:property-placeholder> -->
	<context:component-scan base-package="com.spring"/>
	
	<!-- </context:component-scan> -->
	
	<beans:bean class="org.springframework.jdbc.datasource.DriverManagerDataSource" id="dataSource">
		 <beans:property name="driverClassName" value="${driverClassName}"></beans:property>
		 <beans:property name="url" value="${url}"></beans:property>
		 <beans:property name="username" value="${username}"></beans:property>
		 <beans:property name="password" value="${password}"></beans:property>
	</beans:bean>
	<beans:bean class="org.springframework.orm.hibernate4.LocalSessionFactoryBean" id="sessionFactory">
			<beans:property name="dataSource" ref="dataSource"></beans:property>
			<beans:property name="annotatedClasses">
				  <beans:list>
				   <beans:value>com.spring.model.Employee</beans:value>
				  </beans:list>
 			</beans:property>
	<beans:property name="hibernateProperties">
		<beans:props>
			  <beans:prop key="hibernate.dialect">org.hibernate.dialect.H2Dialect</beans:prop>
			  <beans:prop key="hibernate.show_sql">true</beans:prop>
			  <beans:prop key="hibernate.hbm2ddl.auto">update</beans:prop>
			  <!-- <beans:prop key="h2.console.path">/h2_console</beans:prop>  -->
			   <!-- <mapping class="com.spring.model.Employee"/>   --> 
		</beans:props>
	</beans:property>
</beans:bean>
<!-- <beans:bean id="h2WebServer" class="org.h2.tools.Server" factory-method="createWebServer" init-method="start" destroy-method="stop">
 <beans:constructor-arg value="-web,-webAllowOthers,-webDaemon,-webPort,8082" />
</beans:bean> -->
<beans:bean class="org.springframework.orm.hibernate4.HibernateTransactionManager" id="hibernateTransactionManager">
 <beans:property name="sessionFactory" ref="sessionFactory"></beans:property>
  </beans:bean>

	<!-- Handles HTTP GET requests for /resources/** by efficiently serving up static resources in the ${webappRoot}/resources directory -->
	<resources mapping="/resources/**" location="/resources/" />

	<!-- Resolves views selected for rendering by @Controllers to .jsp resources in the /WEB-INF/views directory -->
	<beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
		<beans:property name="prefix" value="/WEB-INF/views/" />
		<beans:property name="suffix" value=".jsp" />
	</beans:bean>
	
	<context:component-scan base-package="com.spring" />
	
	
	
</beans:beans>


```

#### Step 5 - Add View to project ``Webapp\WEB-INF\view\emp.jsp`` file

```JSP
<?xml version="1.0" encoding="UTF-8"?>
<beans:beans xmlns="http://www.springframework.org/schema/mvc"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:beans="http://www.springframework.org/schema/beans"
	xmlns:context="http://www.springframework.org/schema/context"
	xsi:schemaLocation="http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc.xsd
		http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">

	<!-- DispatcherServlet Context: defines this servlet's request-processing infrastructure -->
	
	<!-- Enables the Spring MVC @Controller programming model -->
	<annotation-driven />
	<beans:bean id="propertyConfigurer" class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
	  <beans:property name="ignoreUnresolvablePlaceholders" value="true"/>
		<beans:property name="locations">
			<beans:list>
				<beans:value>classpath:database.properties</beans:value><!-- "src/main/webapp/WEB-INF/spring/appServlet/database.properties" -->
			</beans:list>
		</beans:property>
	</beans:bean>
	
	<!-- <tx:annotation-driven transaction-manager="hibernateTransactionManager"/> -->
	<beans:bean id="transactionManager" class="org.springframework.orm.hibernate4.HibernateTransactionManager" >
		<beans:property name="sessionFactory" ref="sessionFactory"></beans:property>
	</beans:bean>
	<!-- <tx:annotation-driven transaction-manager="transactionManager"/> -->

	<!-- <context:property-placeholder location="classpath:database.properties"/> -->
	<!-- </context:property-placeholder> -->
	<context:component-scan base-package="com.spring"/>
	
	<!-- </context:component-scan> -->
	
	<beans:bean class="org.springframework.jdbc.datasource.DriverManagerDataSource" id="dataSource">
		 <beans:property name="driverClassName" value="${driverClassName}"></beans:property>
		 <beans:property name="url" value="${url}"></beans:property>
		 <beans:property name="username" value="${username}"></beans:property>
		 <beans:property name="password" value="${password}"></beans:property>
	</beans:bean>
	<beans:bean class="org.springframework.orm.hibernate4.LocalSessionFactoryBean" id="sessionFactory">
			<beans:property name="dataSource" ref="dataSource"></beans:property>
			<beans:property name="annotatedClasses">
				  <beans:list>
				   <beans:value>com.spring.model.Employee</beans:value>
				  </beans:list>
 			</beans:property>
	<beans:property name="hibernateProperties">
		<beans:props>
			  <beans:prop key="hibernate.dialect">org.hibernate.dialect.H2Dialect</beans:prop>
			  <beans:prop key="hibernate.show_sql">true</beans:prop>
			  <beans:prop key="hibernate.hbm2ddl.auto">update</beans:prop>
			  <!-- <beans:prop key="h2.console.path">/h2_console</beans:prop>  -->
			   <!-- <mapping class="com.spring.model.Employee"/>   --> 
		</beans:props>
	</beans:property>
</beans:bean>
<!-- <beans:bean id="h2WebServer" class="org.h2.tools.Server" factory-method="createWebServer" init-method="start" destroy-method="stop">
 <beans:constructor-arg value="-web,-webAllowOthers,-webDaemon,-webPort,8082" />
</beans:bean> -->
<beans:bean class="org.springframework.orm.hibernate4.HibernateTransactionManager" id="hibernateTransactionManager">
 <beans:property name="sessionFactory" ref="sessionFactory"></beans:property>
  </beans:bean>

	<!-- Handles HTTP GET requests for /resources/** by efficiently serving up static resources in the ${webappRoot}/resources directory -->
	<resources mapping="/resources/**" location="/resources/" />

	<!-- Resolves views selected for rendering by @Controllers to .jsp resources in the /WEB-INF/views directory -->
	<beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
		<beans:property name="prefix" value="/WEB-INF/views/" />
		<beans:property name="suffix" value=".jsp" />
	</beans:bean>
	
	<context:component-scan base-package="com.spring" />
	
	
	
</beans:beans>

```

# That's it... you are ready to run

> Right Click on Project > Run As > Run on Server > Select Tomcat Server and click ``finish``


## Meta

Pratik Joshi - pratik.joshi7859@gmail.com

Distributed under the GPL V3.0 license. See ``LICENSE`` for more information.
