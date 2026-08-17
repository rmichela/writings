# The 80-80-80 Rule of Platform Design

One-hundred-percent solutions are exceptionally difficult to design. The one-size-fits-all approach either ends up too restrictive, with many unsupported or partially supported edge cases, or so broad that it loses focus and ends up nearly impossible to maintain.

Consider these examples:

- The Kubernetes platform, which struggles to accommodate long-lived, stateful services.
- The Istio service mesh, which has trouble routing protocols not built around HTTP.
- Buildkite CI/CD, which becomes a fused superset of build, test, integration, artifact deployment, and infrastructure automation.
- A legacy infrastructure automation system, which attempts to tackle everything from VM orchestration, deployment pipelines, secrets management, DNS lifecycle, IAM policy, AWS cost reduction, artifact taxonomy, and engineering-wide role-based access control - all from a single monolith.

They all suffer from the same problem. They struggle with complexity by trying to be a 100% solution.

## 80% is Often Enough

The key insight of the 80-80-80 Rule is that a tightly designed 80% solution is often superior to a caveat-riddled or over-engineered 100% solution. Instead of trying to solve a broad problem completely, for everybody, forever, we break the problem space into four cohorts, and solve separately for each.

- **The first 80%** - The primary solution that works in most cases for most users.
- **The 80% of the rest** - An independent second solution that works for most cases where the primary solution doesn't apply. (There might actually be more than one secondary solution.)
- **The 80% long tail** - An escape hatch alternative that at least allows outliers who can't use the first two solutions to interoperate.
- **The remaining 0.8%** - Find an alternative.

![Bar chart showing: Platform OTK — 80%, Platform VMs and LBs — 16%, self-managed AWS — 4%](/images/pareto_support_tiers.png)

## 80-80-80 In Practice

Service compute is a good example that demonstrates the 80-80-80 rule.

- **The first 80%** - Platform managed Kubernetes. Kubernetes works great for stateless HTTP services, which are typically the majority of services in your enterprise.
- **The 80% of the rest** - Platform managed VMs and AWS load balancers, which give sessionful and stateful services more fine-grained control over instance lifecycle and network protocols.
- **The 80% long tail** - An escape hatch for self-managed AWS resources using Terraform, which allow services like database servers and Lambdas to deploy in configurations not directly supported by the platform tooling.
- **The remaining 0.8%** - Elastic Beanstalk workloads should probably look for other options.

![Nested rectangles diagram showing coverage percentages: Primary solution (80%), Secondary solution (16%), Escape hatch alternative (3.2%), Find another solution (0.8%)](/images/platform_distribution_horizontal_pie.png)

## In Summary

1. Trying to solve hard problems with a 100% solution often under-delivers.
2. It's better to solve the core 80% of a problem well, than to try to account for every outlier.
3. Stacking two 80% solutions gives 96% coverage, with an escape hatch for the last 4%.
4. Extreme outliers should seek alternatives.
