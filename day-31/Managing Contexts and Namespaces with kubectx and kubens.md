### Managing Contexts and Namespaces with kubectx and kubens

### **1. `kubectx`**
**`kubectx`** is a command-line tool used to switch between multiple Kubernetes contexts quickly. A **Kubernetes context** is a combination of a cluster, user, and namespace, which determines the environment that `kubectl` will interact with.

#### **How to Use `kubectx`**:

1. **List available contexts**:
   ```bash
   kubectx
   ```
   This will display all the available contexts that you can switch between.

2. **Switch to a specific context**:
   ```bash
   kubectx <context-name>
   ```
   Replace `<context-name>` with the name of the context you want to switch to. After switching, `kubectl` will use this context by default.

3. **Set the current context to a specific one**:
   ```bash
   kubectx <context-name>
   ```

4. **Show the current context**:
   ```bash
   kubectl config current-context
   ```

5. **Delete a context**:
   ```bash
   kubectx -d <context-name>
   ```
   This will remove a specific context from your configuration.

---

### **2. `kubens`**
**`kubens`** is a utility for switching between Kubernetes namespaces quickly. It works similarly to `kubectx`, but specifically for namespaces within a given context.

#### **How to Use `kubens`**:

1. **List available namespaces**:
   ```bash
   kubens
   ```
   This command will list all the namespaces in the current Kubernetes context.

2. **Switch to a specific namespace**:
   ```bash
   kubens <namespace-name>
   ```
   Replace `<namespace-name>` with the name of the namespace you want to switch to. After switching, `kubectl` will operate within this namespace.

3. **Show the current namespace**:
   ```bash
   kubectl config view --minify | grep namespace:
   ```

4. **Set the current namespace**:
   You can also change the namespace in your Kubernetes configuration using `kubectl`:
   ```bash
   kubectl config set-context --current --namespace=<namespace-name>
   ```

---

### **Why Use `kubectx` and `kubens`?**

- **Efficiency**: They simplify switching between clusters (`kubectx`) and namespaces (`kubens`) without needing to manually type long `kubectl` commands or modify config files.
- **Usability**: They make working with multiple Kubernetes environments much easier by keeping your workflow streamlined and reducing the number of commands you need to memorize.
