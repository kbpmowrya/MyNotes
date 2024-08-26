	<properties>
		<keycloak.version>22.0.4</keycloak.version>
		<resteasy.version>6.2.5.Final</resteasy.version>
	</properties>
		<dependency>
			<groupId>org.keycloak</groupId>
			<artifactId>keycloak-admin-client</artifactId>
			<version>${keycloak.version}</version>
		</dependency>

		<dependency>
			<groupId>org.jboss.resteasy</groupId>
			<artifactId>resteasy-client</artifactId>
			<version>${resteasy.version}</version>
		</dependency>

		<dependency>
			<groupId>org.jboss.resteasy</groupId>
			<artifactId>resteasy-jackson2-provider</artifactId>
			<version>${resteasy.version}</version>
		</dependency>


import org.keycloak.OAuth2Constants;
import org.keycloak.admin.client.Keycloak;
import org.keycloak.admin.client.KeycloakBuilder;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class Beans {

    @Value("${keycloak.adminClientId}")
    private String adminClientId;

    @Value("${keycloak.adminClientSecret}")
    private String adminClientSecret;

    @Value("${keycloak.urls.auth}")
    private String authServerUrl;

    @Value("${keycloak.realm}")
    private String realm;

    @Bean
    public Keycloak keycloak(){


        return KeycloakBuilder.builder()
                .serverUrl(authServerUrl)
                .realm(realm)
                .grantType(OAuth2Constants.CLIENT_CREDENTIALS)
                .clientId(adminClientId)
                .clientSecret(adminClientSecret)
                .build();
    }
}


`import org.keycloak.OAuth2Constants;
import org.keycloak.admin.client.Keycloak;
import org.keycloak.admin.client.KeycloakBuilder;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class Beans {

    @Value("${keycloak.adminClientId}")
    private String adminClientId;

    @Value("${keycloak.adminClientSecret}")
    private String adminClientSecret;

    @Value("${keycloak.urls.auth}")
    private String authServerUrl;

    @Value("${keycloak.realm}")
    private String realm;

    @Bean
    public Keycloak keycloak(){


        return KeycloakBuilder.builder()
                .serverUrl(authServerUrl)
                .realm(realm)
                .grantType(OAuth2Constants.CLIENT_CREDENTIALS)
                .clientId(adminClientId)
                .clientSecret(adminClientSecret)
                .build();
    }
}`
