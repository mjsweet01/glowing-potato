Email notifications for {% ifversion fpt or ghes > 2.21 %}{% data variables.product.prodname_dependabot_alerts %}{% else %}security alerts{% endif %} that affect one or more repositories include the `X-GitHub-Severity`  header field. You can use the value of the `X-GitHub-Severity` header field to filter email notifications for {% ifversion fpt or ghes > 2.21 %}{% data variables.product.prodname_dependabot_alerts %}{% else %}security alerts{% endif %}.