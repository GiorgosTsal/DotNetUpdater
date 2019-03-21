
# SharpUpdate
SharpUpdate is written in C#. It reads a xml file on the server that contains update information such as version, MD5, and update log, download the update, close the current app, and open the updated app in 5 seconds.

# How to use?

### WinForms
 
 For example, in a simple WinForms class, simply add:

```C#
public partial class Form1 : Form
{
    private SharpUpdater updater;

    public Form1()
    {
        InitializeComponent();

        updater = new SharpUpdater(Assembly.GetExecutingAssembly(), this, new Uri("update-xml-location"));
    }

    private void button1_Click(object sender, EventArgs e)
    {
        updater.DoUpdate();
    }
}
```

### XML

For details on the xml on the server with update information, please check out the sample "project.xml". A basic structure is as following:

```xml
<?xml version="1.0"?> 
<sharpUpdate> 
    <update> 
        <version></version> 
        <url></url> 
        <filePath></filePath>
        <md5></md5>
        <description></description> 
        <launchArgs></launchArgs> 
    </update>
    
    <add> 
        <version></version> 
        <url></url> 
        <filePath></filePath>
        <md5></md5>
        <description></description> 
        <launchArgs></launchArgs> 
    </add>
    
    <remove>
        <filePath></filePath>
        <description></description> 
        <launchArgs></launchArgs> 
    </remove>
</sharpUpdate>
```

# Acknowledgments
SharpUpdate is a modified copy from AutoUpdater by BetterCoder on Youtube. His tutorial can be found here: http://goo.gl/n7btY
