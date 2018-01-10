// UI Action
var passVariable = {
    prefix: 'pv_',

    client: function () {
        var glideModal = new GlideModal('select_something', false, 400);
        glideModal.setTitle('Select Something');
        glideModal.render();
    },

    setVariable: function (name, value) {
        name = this.prefix + name;
        var existing = document.getElementsByName(name);

        if (existing.length > 0) {
            existing[0].value = value;
        } else {
            var hiddenInput = document.createElement('input');
            hiddenInput.setAttribute('type', 'hidden');
            hiddenInput.setAttribute('name', name);
            hiddenInput.setAttribute('value', value);
            g_form.getFormElement().appendChild(hiddenInput);
        }

    },

    server: function () {
        var parameterKeys = RP.getParameters().keySet().toArray();
        
        for(var i = 0; i < parameterKeys.length; i++){
            var parameterKey = parameterKeys[i];
            if(parameterKey.indexOf(this.prefix) == 0 ){
                gs.addInfoMessage(parameterKey + ' = ' + RP.getParameterValue(parameterKey));
            }
        }

    }
};

if (typeof window === 'undefined') passVariable.server();
