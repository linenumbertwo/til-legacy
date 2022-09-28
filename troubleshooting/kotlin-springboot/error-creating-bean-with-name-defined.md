### Error Code

```shell
org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'entityManagerFactory' defined in class path resource [org/springframework/boot/autoconfigure/orm/jpa/HibernateJpaConfiguration.class]: 
Invocation of init method failed; nested exception is javax.persistence.PersistenceException: [PersistenceUnit: default] Unable to build Hibernate SessionFactory; nested exception is org.hibernate.tool.schema.spi.SchemaManagementException: Schema-validation: missing table [files]
```

### Solution
application.properties 파일에 `spring.jpa.hibernate.ddl-auto`의 값이 `validate`로 되어있었는데 이를 `create`로 바꾸어주니 에러도 사라지고 테이블도 정상적으로 생성되었다.

#### ddl-auto option
- `create`: SessionFactory 시작 시 스키마를 삭제하고 다시 생성
- `create-drop`: SessionFactory 종료 시 스키마를 삭제
- `update`: SessionFactory 와  연결된 DB를 비교하여 추가된 항목은 추가
- `validate`: SessionFactory 시작 시 객체구성과 스키마가 다르다면 예외 발생
- `none`: 진짜 아무것도 안함

실제 서비스 배포시에는 `none` 외에 사용하면 안될거같은데 개발 과정 중에는 유용하게 사용될거같다. 


