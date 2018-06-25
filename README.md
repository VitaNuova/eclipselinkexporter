### EclipseLink support for Prometheus Java Instrumentation library

This is EclipseLink exporter for Prometheus Java instrumentation library. It follows the same pattern as the Hibernate exporter from the Prometheus Java Instrumentation library https://github.com/prometheus/client_java.

This exporter can be used to collect metrics from one or more EclipseLink Session instances.
<p>
 Usage example for a single session:
 <pre>
 new prometheus.exporter.EclipseLinkStatisticsCollector(session, "name").register();
 </pre>
 Usage example for multiple sessions:
 <pre>
 new prometheus.exporter.EclipseLinkStatisticsCollector()
     .add(session1, "name1")
     .add(session2, "name2")
     .register();
 </pre>
 Session instance can be obtained from EntityManager instance like this:
 <pre>
 Session session = ((JpaEntityManager)entityManager.getDelegate()).getSession();
 </pre>
 </p>


