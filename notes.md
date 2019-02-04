```js

let fields = {
    type: Type, //done
    unique: Boolean, //done
    index: Boolean, //done
    deprecated: String, //done
    arguments: String, //done
    resolve: Function, //done
    nullable: Boolean,
    hidden: Boolean, //done
    setter: Function,
    getter: Function,
    default: var | Function
}

async function createIndexes(){
    let indexes = getIndexesRecursive(fields)
    for(let i in indexes){
        await collection.createIndex(indexes[i])
    }
}

function getIndexesRecursive(fields){
    let indexes = []

    for(let name in fields){
        let schema = fields[name]
        let indexFieldConfig = {}
        if(schema.unique === true) indexFieldConfig.unique = true
        if(schema.index === true) indexes.push([{name: 1}, indexFieldConfig}])
    }

    return indexes
}

function resolveFields(fields){
    let fieldResults = []

    for(let name in fields){
        let schema = fields[name]
        if(schema.hidden) continue

        fieldResults.push(resolveField(schema))
    }

    return fieldResults.join('\n')
}

function translateType(schema){

}

function resolveField(schema){
    let name = schema.name
    let args = schema.arguments ? `(${schema.arguments})` : ''
    let type = translateType(schema.type)
    let deprecated = schema.deprecated ? ` @deprecated(reason: "${schema.deprecated}"` : ''

    let line = `${name}${args}: ${type}${deprecated}`
}

class User{
    static get mutationSchema(){
        return `
        mutation login {
            
        }
        `
    }
}

```